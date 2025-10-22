<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>UCM Scholarship Portal - Home/Search</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>
<script>
    tailwind.config = {
        theme: {
            extend: {
                colors: {
                    'ucm-red': '#990000',
                    'ucm-gold': '#ffcc00',
                    'ucm-light': '#fefefe',
                    'ucm-surface': '#f9fafb',
                },
                fontFamily: {
                    sans: ['Inter', 'sans-serif'],
                },
            }
        }
    }

    function switchView(viewId) {
        const views = ['view-home', 'view-results']; 
        const navElements = {
            'view-home': document.getElementById('nav-home'),
            'view-results': document.getElementById('nav-results')
        };

        views.forEach(id => {
            const element = document.getElementById(id);
            if (element) element.classList.add('hidden');
        });

        const newView = document.getElementById(viewId);
        if (newView) {
            newView.classList.remove('hidden');
            newView.scrollTop = 0;

            Object.keys(navElements).forEach(id => {
                const isSelected = id === viewId;
                const navButton = navElements[id];
                navButton.classList.toggle('bg-ucm-gold', isSelected);
                navButton.classList.toggle('bg-white', !isSelected);
                navButton.classList.toggle('text-ucm-red', true);
                navButton.classList.toggle('font-extrabold', isSelected);
                navButton.classList.toggle('font-semibold', !isSelected);
                navButton.classList.toggle('border-ucm-red', !isSelected);
                navButton.classList.toggle('border-transparent', isSelected);
            });
        }
    }

    function openModal() {
        const modal = document.getElementById('detail-modal');
        if (modal) modal.classList.remove('hidden');
    }

    function closeModal() {
        const modal = document.getElementById('detail-modal');
        if (modal) modal.classList.add('hidden');
    }

    document.addEventListener('DOMContentLoaded', () => {
        switchView('view-home');
    });
</script>
<style>
    body {
        font-family: 'Inter', sans-serif;
        background-color: #e5e7eb;
        min-height: 100vh;
        display: flex;
        justify-content: center;
        padding-top: 20px;
    }
    #template-container {
        width: 100%;
        max-width: 1080px;
        min-height: 100vh;
        margin: 0 auto;
        box-shadow: 0 15px 50px rgba(0,0,0,0.2);
        display: flex;
        flex-direction: column;
        border-radius: 12px;
        overflow: hidden;
        padding: 0 1rem; /* fluid padding for mobile */
    }
    main::-webkit-scrollbar {
        width: 12px;
    }
    main::-webkit-scrollbar-track {
        background: #e5e7eb;
    }
    main::-webkit-scrollbar-thumb {
        background-color: #d1d5db;
        border-radius: 20px;
        border: 3px solid #e5e7eb;
    }
</style>
</head>
<body class="antialiased text-gray-800">

<div id="template-container" class="bg-ucm-surface">

    <!-- Top Bar -->
    <div class="flex-shrink-0 w-full h-12 bg-ucm-red text-white flex justify-between items-center px-4 sm:px-6 text-lg sm:text-xl font-medium">
        <span>9:16</span>
        <div class="flex items-center space-x-2">
            <svg class="w-5 h-5 sm:w-6 sm:h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M12 4.07V2.5A1.5 1.5 0 0113.5 1h-3A1.5 1.5 0 019 2.5v1.57A8 8 0 1012 20a8 8 0 000-15.93zM12 18a6 6 0 110-12 6 6 0 010 12z"></path></svg>
            <svg class="w-5 h-5 sm:w-6 sm:h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M19 12h-2V6h-4V4h4V2h2v2h2v2h-2v6zM4 18h16v-2H4v2zm0-4h16v-2H4v2z"></path></svg>
            <svg class="w-6 h-6 sm:w-8 sm:h-8" fill="currentColor" viewBox="0 0 24 24"><path d="M17 5v14c0 1.1-.9 2-2 2H9c-1.1 0-2-.9-2-2V5c0-1.1.9-2 2-2h6c1.1 0 2 .9 2 2zM9 5h6v14H9V5z"></path></svg>
        </div>
    </div>

    <!-- Header -->
    <header class="bg-ucm-red shadow-lg flex-shrink-0 px-4 sm:px-10 py-4 sm:py-6 flex flex-col sm:flex-row justify-between items-center">
        <div class="flex items-center space-x-3 sm:space-x-5 cursor-pointer mb-3 sm:mb-0" onclick="switchView('view-home')">
            <div class="w-12 h-12 sm:w-16 sm:h-16 bg-white rounded-full flex items-center justify-center text-ucm-red font-extrabold text-2xl sm:text-3xl">
                UCM
            </div>
            <h1 class="text-2xl sm:text-4xl font-bold text-white tracking-wide">
                Scholarship Portal
            </h1>
        </div>

        <nav class="flex flex-wrap justify-center sm:justify-end items-center gap-2 sm:gap-6">
            <button id="nav-home" onclick="switchView('view-home')" class="bg-ucm-gold text-ucm-red font-extrabold py-2 px-4 sm:py-3 sm:px-8 text-base sm:text-xl rounded-xl shadow-md hover:opacity-90 transition duration-300 border-transparent">
                Scholarship Search
            </button>
            <button id="nav-results" onclick="switchView('view-results')" class="bg-white text-ucm-red font-semibold py-2 px-4 sm:py-3 sm:px-8 text-base sm:text-xl rounded-xl shadow-md hover:bg-gray-100 transition duration-300 border-2 border-ucm-red">
                My Decisions
            </button>
            <button class="p-2 sm:p-3 text-white rounded-full hover:bg-white/20 transition-colors" title="Help & Information">
                <svg class="w-6 h-6 sm:w-8 sm:h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
            </button>
        </nav>
    </header>

    <!-- Home View -->
    <main id="view-home" class="flex-grow w-full p-4 sm:p-10 overflow-y-auto space-y-8">

        <!-- Hero Section -->
        <section class="bg-white p-6 sm:p-10 rounded-2xl shadow-xl border-t-8 border-ucm-red">
            <h2 class="text-2xl sm:text-4xl font-extrabold text-gray-900 mb-3 flex items-center">
                <svg class="w-6 sm:w-10 h-6 sm:h-10 text-ucm-gold mr-2 sm:mr-4" fill="currentColor" viewBox="0 0 20 20"><path d="M5 4a2 2 0 012-2h6a2 2 0 012 2v14l-5-2.5L5 18V4z"></path></svg>
                Find Your Funding
            </h2>
            <p class="text-base sm:text-xl text-gray-600 mb-4 sm:mb-6">
                Welcome to the UCM Scholarship Portal! Use the tools below to explore all available scholarship opportunities, grants, and awards. Be sure to complete the General Application to be matched with dozens of awards automatically.
            </p>
            <a href="#" class="inline-block bg-ucm-gold text-ucm-red font-extrabold py-2 sm:py-3 px-4 sm:px-8 text-base sm:text-xl rounded-xl shadow-lg hover:bg-opacity-80 transition duration-300">
                Complete General Application &rarr;
            </a>
        </section>

        <!-- Filter Sidebar (stacked on mobile) -->
        <aside class="bg-white p-4 sm:p-8 rounded-2xl shadow-xl border border-gray-100">
            <h2 class="text-2xl sm:text-3xl font-bold text-gray-900 mb-4 sm:mb-6 border-b pb-2 sm:pb-3">Filter Opportunities</h2>
            <div class="mb-4 sm:mb-6">
                <label for="keyword-search" class="block text-sm sm:text-lg font-medium text-gray-700 mb-1 sm:mb-2">Search by Keyword</label>
                <input type="text" id="keyword-search" placeholder="e.g., Biology, Leadership" class="w-full p-2 sm:p-4 text-sm sm:text-xl border-2 border-gray-300 rounded-xl focus:ring-ucm-red focus:border-ucm-red transition-shadow">
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 sm:gap-6 mb-4 sm:mb-6">
                <div>
                    <label for="department-filter" class="block text-sm sm:text-lg font-medium text-gray-700 mb-1 sm:mb-2">Department Scope</label>
                    <div class="relative">
                        <select id="department-filter" class="w-full p-2 sm:p-4 text-sm sm:text-xl border-2 border-gray-300 rounded-xl bg-white focus:ring-ucm-red focus:border-ucm-red transition-shadow appearance-none">
                            <option>All Departments (54)</option>
                            <option>College of Arts, Humanities...</option>
                            <option>Harmon College of Business (12)</option>
                            <option>Department of Agriculture (4)</option>
                            <option>School of Nursing (8)</option>
                        </select>
                        <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 sm:px-4 text-gray-700">
                            <svg class="w-4 h-4 sm:w-6 sm:h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                        </div>
                    </div>
                </div>

                <div>
                    <h3 class="text-sm sm:text-lg font-medium text-gray-700 mb-1 sm:mb-2">Award Type</h3>
                    <div class="grid grid-cols-2 gap-2 sm:gap-3">
                        <label class="flex items-center text-sm sm:text-base text-gray-600">
                            <input type="checkbox" class="h-4 w-4 sm:h-6 sm:w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red" checked>
                            <span class="ml-1 sm:ml-2">Scholarship (40)</span>
                        </label>
                        <label class="flex items-center text-sm sm:text-base text-gray-600">
                            <input type="checkbox" class="h-4 w-4 sm:h-6 sm:w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red">
                            <span class="ml-1 sm:ml-2">Grant (8)</span>
                        </label>
                        <label class="flex items-center text-sm sm:text-base text-gray-600">
                            <input type="checkbox" class="h-4 w-4 sm:h-6 sm:w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red">
                            <span class="ml-1 sm:ml-2">Award/Prize (6)</span>
                        </label>
                        <label class="flex items-center text-sm sm:text-base text-gray-600">
                            <input type="checkbox" class="h-4 w-4 sm:h-6 sm:w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red">
                            <span class="ml-1 sm:ml-2">Pending (2)</span>
                        </label>
                    </div>
                </div>
            </div>
            <button class="w-full bg-ucm-red text-white font-extrabold text-base sm:text-xl py-2 sm:py-3 rounded-xl shadow-lg hover:opacity-90 transition-opacity">
                Apply Filters
            </button>
        </aside>

        <!-- Opportunities Section -->
        <section class="space-y-6">

            <div class="flex flex-col space-y-4">
                <!-- Scholarship Card Example -->
                <div class="bg-white p-4 sm:p-6 rounded-2xl shadow-xl border border-gray-100 hover:shadow-2xl transition duration-200 cursor-pointer" onclick="openModal()">
                    <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center">
                        <h3 class="text-lg sm:text-2xl font-bold text-gray-900 hover:text-ucm-red transition-colors">
                            <a href="#" onclick="event.preventDefault(); event.stopPropagation();">A. Ralph Boxell Eagle Scout Scholarship</a>
                        </h3>
                        <button class="mt-2 sm:mt-0 text-gray-400 hover:text-ucm-red transition-colors" title="Save Opportunity" onclick="event.stopPropagation()">
                            <svg class="w-6 h-6 sm:w-8 sm:h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z"></path></svg>
                        </button>
                    </div>

                    <p class="text-sm sm:text-lg text-gray-600 mt-2 mb-4">
                        Available through the UCM Alumni Foundation for active Eagle Scouts enrolled at UCM.
                    </p>

                    <div class="flex flex-wrap items-center text-xs sm:text-base">
                        <span class="bg-gray-100 text-gray-700 font-medium px-2 sm:px-4 py-1 rounded-full mr-2 sm:mr-3 mb-2">
                            Amount: Varies
                        </span>
                        <span class="bg-ucm-gold/20 text-ucm-red font-semibold px-2 sm:px-4 py-1 rounded-full mr-2 sm:mr-3 mb-2">
                            Deadline: Mar 15, 2026
                        </span>
                        <span class="bg-ucm-red/10 text-ucm-red px-2 sm:px-4 py-1 rounded-full mr-2 sm:mr-3 mb-2">
                            General Application
                        </span>
                    </div>
                </div>

                <!-- More scholarship cards can follow same responsive structure -->
            </div>
        </section>

    </main>

    <!-- Results View (hidden initially) -->
    <main id="view-results" class="hidden flex-grow w-full p-4 sm:p-10 overflow-y-auto space-y-8">
        <!-- Similar responsive adjustments as home view -->
        <!-- ... -->
    </main>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white flex-shrink-0 py-4 px-4 sm:px-10 text-center text-sm sm:text-lg">
        <p class="text-gray-400">&copy; 2025 University of Central Missouri. Financial Aid & Scholarship Office.</p>
    </footer>

</div>

<!-- Modal -->
<div id="detail-modal" class="hidden fixed inset-0 bg-gray-900 bg-opacity-75 z-50 flex justify-center items-center p-2 sm:p-4" onclick="closeModal()">
    <div class="bg-white w-full max-w-5xl max-h-[90vh] rounded-2xl shadow-2xl transform transition-all overflow-y-auto text-base sm:text-2xl" onclick="event.stopPropagation()">
        <div class="sticky top-0 bg-white p-4 sm:p-8 border-b flex justify-between items-start z-10">
            <h2 class="text-lg sm:text-4xl font-extrabold text-ucm-red">A. Ralph Boxell Eagle Scout Scholarship</h2>
            <button onclick="closeModal()" class="text-gray-400 hover:text-gray-800 transition-colors p-2 rounded-full" title="Close">
                <svg class="w-6 sm:w-10 h-6 sm:h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
            </button>
        </div>
        <div class="p-4 sm:p-8 space-y-4 sm:space-y-8">
            <!-- Modal content -->
            <!-- ... -->
        </div>
    </div>
</div>

</body>
</html>
