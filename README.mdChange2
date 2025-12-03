@@ -1,266 +1,449 @@
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UCM Scholarship Portal - Home/Search</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        // Tailwind custom configuration
        // Custom Tailwind Configuration
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

        /**
         * Function to switch between the main application views (Home/Search and Decisions).
         * @param {string} viewId - The ID of the view to display ('view-home' or 'view-results').
         */
        function switchView(viewId) {
            const views = ['view-home', 'view-results'];
            const navElements = {
                'view-home': document.getElementById('nav-home'),
                'view-results': document.getElementById('nav-results')
            };

            // Update view IDs from 'view-search' to 'view-home'
            const views = ['view-home', 'view-results']; 
            views.forEach(id => {
                const element = document.getElementById(id);
                if (element) element.classList.add('hidden');
                if (element) {
                    element.classList.add('hidden');
                }
            });

            const newView = document.getElementById(viewId);
            if (newView) {
                newView.classList.remove('hidden');
                // Ensure the view scrolls to the top when switched
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
                // Simple navigation button highlighting logic
                document.getElementById('nav-home').classList.toggle('bg-ucm-gold', viewId === 'view-home');
                document.getElementById('nav-home').classList.toggle('bg-white', viewId !== 'view-home');
                document.getElementById('nav-results').classList.toggle('bg-white', viewId === 'view-home');
                document.getElementById('nav-results').classList.toggle('bg-ucm-gold', viewId !== 'view-home');

                // Swap text colors based on selected view
                document.getElementById('nav-home').classList.toggle('text-ucm-red', viewId === 'view-home');
                document.getElementById('nav-results').classList.toggle('text-ucm-red', viewId !== 'view-home');
            }
        }

        // JavaScript for Modal Functionality
        function openModal() {
            document.getElementById('detail-modal')?.classList.remove('hidden');
            const modal = document.getElementById('detail-modal');
            if (modal) {
                modal.classList.remove('hidden');
            }
        }

        function closeModal() {
            document.getElementById('detail-modal')?.classList.add('hidden');
            const modal = document.getElementById('detail-modal');
            if (modal) {
                modal.classList.add('hidden');
            }
        }

        
        // Initial view load function (set the home view as default on load)
        document.addEventListener('DOMContentLoaded', () => {
            switchView('view-home');
        });
    </script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #e5e7eb;
            background-color: #e5e7eb; /* Background for the surrounding viewport */
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            align-items: flex-start; /* Start from the top */
            padding-top: 20px;
        }

        /* Scrollbar styling */
        /* CRITICAL: Fixed dimensions for the 1080x1920 template */
        #template-container {
            width: 1080px;
            height: 1920px;
            /* Center the template and give it depth */
            margin: 0 auto;
            box-shadow: 0 15px 50px rgba(0,0,0,0.2);
            display: flex;
            flex-direction: column;
            border-radius: 12px;
            overflow: hidden; /* Ensures contents stay within the fixed frame */
        }

        /* Custom scrollbar styling for the content areas */
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

    <div id="template-container" class="w-full max-w-[1080px] sm:max-w-[800px] md:max-w-[1080px] mx-auto bg-ucm-surface flex flex-col shadow-lg rounded-xl overflow-hidden">

        <!-- Status Bar -->
        <div class="flex-shrink-0 w-full h-12 bg-ucm-red text-white flex justify-between items-center px-4 sm:px-6 md:px-10 text-lg sm:text-xl font-medium">
            <span>9:16</span>
            <div class="flex items-center space-x-2">
                <svg class="w-5 h-5 sm:w-6 sm:h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M12 4.07V2.5A1.5 1.5 0 0113.5 1h-3A1.5 1.5 0 019 2.5v1.57A8 8 0 1012 20a8 8 0 000-15.93zM12 18a6 6 0 110-12 6 6 0 010 12z"></path></svg>
                <svg class="w-5 h-5 sm:w-6 sm:h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M19 12h-2V6h-4V4h4V2h2v2h2v2h-2v6zM4 18h16v-2H4v2zm0-4h16v-2H4v2z"></path></svg>
                <svg class="w-6 h-6 sm:w-8 sm:h-8" fill="currentColor" viewBox="0 0 24 24"><path d="M17 5v14c0 1.1-.9 2-2 2H9c-1.1 0-2-.9-2-2V5c0-1.1.9-2 2-2h6c1.1 0 2 .9 2 2zM9 5h6v14H9V5z"></path></svg>
            </div>
        </div>
    <div id="template-container" class="bg-ucm-surface">

        <!-- Header -->
        <header class="bg-ucm-red shadow-lg flex-shrink-0 p-4 sm:p-6 md:p-10 flex flex-col sm:flex-row justify-between items-center">
            <div class="flex items-center space-x-4 sm:space-x-5 cursor-pointer mb-4 sm:mb-0" onclick="switchView('view-home')">
                <div class="w-12 h-12 sm:w-16 sm:h-16 bg-white rounded-full flex items-center justify-center text-ucm-red font-extrabold text-xl sm:text-3xl">
                    UCM
        <header class="bg-ucm-red shadow-lg flex-shrink-0 h-32 px-10 py-6">
            <div class="flex justify-between items-center h-full">
                <div class="flex items-center space-x-5 cursor-pointer" onclick="switchView('view-home')">
                    <div class="w-16 h-16 bg-white rounded-full flex items-center justify-center text-ucm-red font-extrabold text-3xl">
                        UCM
                    </div>
                    <h1 class="text-4xl font-bold text-white tracking-wide">
                        Scholarship Portal
                    </h1>
                </div>
                <h1 class="text-2xl sm:text-4xl font-bold text-white tracking-wide">
                    Scholarship Portal
                </h1>
            </div>

            <nav class="flex flex-wrap justify-center sm:justify-end items-center gap-2 sm:gap-6">
                <button id="nav-home" onclick="switchView('view-home')" class="bg-ucm-gold text-ucm-red font-extrabold py-2 px-4 sm:py-3 sm:px-8 text-lg sm:text-xl rounded-xl shadow-md hover:opacity-90 transition">
                    Scholarship Search
                </button>
                <button id="nav-results" onclick="switchView('view-results')" class="bg-white text-ucm-red font-semibold py-2 px-4 sm:py-3 sm:px-8 text-lg sm:text-xl rounded-xl shadow-md hover:bg-gray-100 transition border-2 border-ucm-red">
                    My Decisions
                </button>
                <button class="p-2 sm:p-3 text-white rounded-full hover:bg-white/20 transition" title="Help & Info">
                    <svg class="w-6 h-6 sm:w-8 sm:h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                </button>
            </nav>
                <nav class="flex items-center space-x-6">
                    <button id="nav-home" onclick="switchView('view-home')" class="bg-ucm-gold text-ucm-red font-semibold py-3 px-8 text-xl rounded-xl shadow-md hover:opacity-90 transition duration-300">
                        Scholarship Search
                    </button>
                    <button id="nav-results" onclick="switchView('view-results')" class="bg-white text-ucm-red font-semibold py-3 px-8 text-xl rounded-xl shadow-md hover:bg-gray-100 transition duration-300 border border-ucm-red">
                        My Decisions
                    </button>
                    <button class="p-3 text-white rounded-full hover:bg-white/20 transition-colors">
                        <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                    </button>
                </nav>
            </div>
        </header>

        <!-- Home/Search View -->
        <main id="view-home" class="flex-grow w-full p-4 sm:p-6 md:p-10 overflow-y-auto space-y-8">
            
            <!-- Intro Section -->
            <section class="bg-white p-6 sm:p-10 rounded-2xl shadow-xl border-t-8 border-ucm-red">
                <h2 class="text-2xl sm:text-4xl font-extrabold text-gray-900 mb-3 flex items-center">
                    <svg class="w-6 h-6 sm:w-10 sm:h-10 text-ucm-gold mr-2 sm:mr-4" fill="currentColor" viewBox="0 0 20 20"><path d="M5 4a2 2 0 012-2h6a2 2 0 012 2v14l-5-2.5L5 18V4z"></path></svg>
                    Find Your Funding
                </h2>
                <p class="text-base sm:text-xl text-gray-600 mb-6">
                    Welcome to the UCM Scholarship Portal! Use the tools below to explore all available scholarship opportunities, grants, and awards. Complete the General Application to be matched with dozens of awards automatically.
                </p>
                <a href="#" class="inline-block bg-ucm-gold text-ucm-red font-extrabold py-2 sm:py-3 px-4 sm:px-8 text-lg sm:text-xl rounded-xl shadow-lg hover:bg-opacity-80 transition">
                    Complete General Application &rarr;
                </a>
            </section>
        <main id="view-home" class="flex-grow w-full p-10 overflow-y-auto">
            <div class="space-y-8">

            <!-- Filter Section -->
            <aside class="bg-white p-4 sm:p-8 rounded-2xl shadow-xl border border-gray-100">
                <h2 class="text-xl sm:text-3xl font-bold text-gray-900 mb-6 border-b pb-3">Filter Opportunities</h2>
                <section class="bg-white p-10 rounded-2xl shadow-xl border-t-8 border-ucm-red flex-shrink-0">
                    <h2 class="text-4xl font-extrabold text-gray-900 mb-3 flex items-center">
                        <svg class="w-10 h-10 text-ucm-gold mr-4" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M5 4a2 2 0 012-2h6a2 2 0 012 2v14l-5-2.5L5 18V4z"></path></svg>
                        Find Your Funding
                    </h2>
                    <p class="text-xl text-gray-600 mb-6">
                        Welcome to the **UCM Scholarship Portal**! Use the tools below to explore all available scholarship opportunities, grants, and awards. Be sure to complete the **General Application** to be matched with dozens of awards automatically.
                    </p>
                    <a href="#" class="inline-block bg-ucm-gold text-ucm-red font-extrabold py-3 px-8 text-xl rounded-xl shadow-lg hover:bg-opacity-80 transition duration-300">
                        Complete General Application &rarr;
                    </a>
                </section>
                
                ---

                <div class="mb-6">
                    <label for="keyword-search" class="block text-base sm:text-lg font-medium text-gray-700 mb-2">Search by Keyword</label>
                    <input type="text" id="keyword-search" placeholder="e.g., Biology, Leadership" class="w-full p-2 sm:p-4 text-base sm:text-xl border-2 border-gray-300 rounded-xl focus:ring-ucm-red focus:border-ucm-red transition-shadow">
                </div>
                <aside class="bg-white p-8 rounded-2xl shadow-xl border border-gray-100 flex-shrink-0">
                    <h2 class="text-3xl font-bold text-gray-900 mb-6 border-b pb-3">Filter Opportunities</h2>
                    
                    <div class="mb-6">
                        <label for="keyword-search" class="block text-lg font-medium text-gray-700 mb-2">Search by Keyword</label>
                        <input type="text" id="keyword-search" placeholder="e.g., Biology, Leadership" class="w-full p-4 text-xl border-2 border-gray-300 rounded-xl focus:ring-ucm-red focus:border-ucm-red transition-shadow">
                    </div>

                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 sm:gap-6 mb-6">
                    <div>
                        <label for="department-filter" class="block text-base sm:text-lg font-medium text-gray-700 mb-2">Department Scope</label>
                        <div class="relative">
                            <select id="department-filter" class="w-full p-2 sm:p-4 text-base sm:text-xl border-2 border-gray-300 rounded-xl bg-white focus:ring-ucm-red focus:border-ucm-red transition-shadow appearance-none">
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
                        <div>
                            <label for="department-filter" class="block text-lg font-medium text-gray-700 mb-2">Department Scope</label>
                            <select id="department-filter" class="w-full p-4 text-xl border-2 border-gray-300 rounded-xl bg-white focus:ring-ucm-red focus:border-ucm-red transition-shadow appearance-none">
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
                        <h3 class="text-base sm:text-lg font-medium text-gray-700 mb-2">Award Type</h3>
                        <div class="grid grid-cols-2 gap-2 sm:gap-3">
                            <label class="flex items-center text-sm sm:text-base text-gray-600">
                                <input type="checkbox" class="h-4 w-4 sm:h-6 sm:w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red" checked>
                                <span class="ml-2">Scholarship (40)</span>
                            </label>
                            <label class="flex items-center text-sm sm:text-base text-gray-600">
                                <input type="checkbox" class="h-4 w-4 sm:h-6 sm:w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red">
                                <span class="ml-2">Grant (8)</span>
                            </label>
                            <label class="flex items-center text-sm sm:text-base text-gray-600">
                                <input type="checkbox" class="h-4 w-4 sm:h-6 sm:w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red">
                                <span class="ml-2">Award/Prize (6)</span>
                            </label>
                            <label class="flex items-center text-sm sm:text-base text-gray-600">
                                <input type="checkbox" class="h-4 w-4 sm:h-6 sm:w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red">
                                <span class="ml-2">Pending (2)</span>
                            </label>
                        <div>
                            <h3 class="text-lg font-medium text-gray-700 mb-2">Award Type</h3>
                            <div class="grid grid-cols-2 gap-3">
                                <label class="flex items-center text-base text-gray-600">
                                    <input type="checkbox" class="h-6 w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red" checked>
                                    <span class="ml-2">Scholarship (40)</span>
                                </label>
                                <label class="flex items-center text-base text-gray-600">
                                    <input type="checkbox" class="h-6 w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red">
                                    <span class="ml-2">Grant (8)</span>
                                </label>
                                <label class="flex items-center text-base text-gray-600">
                                    <input type="checkbox" class="h-6 w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red">
                                    <span class="ml-2">Award/Prize (6)</span>
                                </label>
                                <label class="flex items-center text-base text-gray-600">
                                    <input type="checkbox" class="h-6 w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red">
                                    <span class="ml-2">Pending (2)</span>
                                </label>
                            </div>
                        </div>
                    </div>
                </div>
                    
                    <button class="w-full bg-ucm-red text-white font-extrabold text-xl py-3 rounded-xl shadow-lg hover:opacity-90 transition-opacity">
                        Apply Filters
                    </button>
                </aside>

                <button class="w-full bg-ucm-red text-white font-extrabold text-lg sm:text-xl py-2 sm:py-3 rounded-xl shadow-lg hover:opacity-90 transition">
                    Apply Filters
                </button>
            </aside>
                ---

            <!-- Opportunities List -->
            <section class="space-y-6">
                <div class="flex justify-between items-center mb-6 border-b pb-3 flex-wrap">
                    <h2 class="text-xl sm:text-3xl font-bold text-gray-900">Opportunities <span class="text-base sm:text-xl font-normal text-gray-500">(54 Total)</span></h2>
                    <div class="flex items-center space-x-2 sm:space-x-3 mt-2 sm:mt-0">
                        <label for="sort-by" class="text-sm sm:text-lg text-gray-600 font-medium">Sort:</label>
                        <div class="relative">
                            <select id="sort-by" class="p-1 sm:p-3 text-sm sm:text-lg border border-gray-300 rounded-xl bg-white appearance-none">
                <section>
                    <div class="flex justify-between items-center mb-6 border-b pb-3">
                        <h2 class="text-3xl font-bold text-gray-900">Opportunities <span class="text-xl font-normal text-gray-500">(54 Total)</span></h2>
                        <div class="flex items-center space-x-3">
                            <label for="sort-by" class="text-lg text-gray-600 font-medium">Sort:</label>
                            <select id="sort-by" class="p-2 text-lg border border-gray-300 rounded-xl">
                                <option>Deadline (Earliest)</option>
                                <option>Award Amount (High to Low)</option>
                                <option>Alphabetical (A-Z)</option>
                            </select>
                            <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-1 sm:px-3 text-gray-700">
                                <svg class="w-3 h-3 sm:w-5 sm:h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                        </div>
                    </div>

                    <div class="space-y-6">
                        <div class="bg-white p-6 rounded-2xl shadow-xl border border-gray-100 hover:shadow-2xl transition duration-200 cursor-pointer" onclick="openModal()">
                            <div class="flex justify-between items-start">
                                <h3 class="text-2xl font-bold text-gray-900 hover:text-ucm-red transition-colors">
                                    <a href="#" onclick="event.preventDefault();">A. Ralph Boxell Eagle Scout Scholarship</a>
                                </h3>
                                <button class="text-gray-400 hover:text-ucm-red transition-colors" title="Save Opportunity">
                                    <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z"></path></svg>
                                </button>
                            </div>
                            
                            <p class="text-gray-600 mt-2 mb-4 text-lg">
                                Available through the UCM Alumni Foundation for active Eagle Scouts enrolled at UCM.
                            </p>
                            
                            <div class="flex flex-wrap items-center text-base">
                                <span class="bg-gray-100 text-gray-700 font-medium px-4 py-1.5 rounded-full mr-3 mb-2">
                                    Amount: Varies
                                </span>
                                <span class="bg-ucm-gold/20 text-ucm-red font-semibold px-4 py-1.5 rounded-full mr-3 mb-2">
                                    Deadline: Mar 15, 2026
                                </span>
                                <span class="bg-ucm-red/10 text-ucm-red px-4 py-1.5 rounded-full mr-3 mb-2">
                                    General Application
                                </span>
                            </div>
                        </div>
                        
                        <div class="bg-white p-6 rounded-2xl shadow-xl border border-gray-100 hover:shadow-2xl transition duration-200 cursor-pointer">
                            <div class="flex justify-between items-start">
                                <h3 class="text-2xl font-bold text-gray-900 hover:text-ucm-red transition-colors">
                                    <a href="#">Harmon College Business Graduate Scholarship</a>
                                </h3>
                                <button class="text-ucm-red transition-colors" title="Remove from Saved">
                                    <svg class="w-8 h-8" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z"></path></svg>
                                </button>
                            </div>
                            
                            <p class="text-gray-600 mt-2 mb-4 text-lg">
                                Established to support outstanding graduate students within the Harmon College of Business & Professional Studies.
                            </p>
                            
                            <div class="flex flex-wrap items-center text-base">
                                <span class="bg-gray-100 text-gray-700 font-medium px-4 py-1.5 rounded-full mr-3 mb-2">
                                    Amount: Full Ride
                                </span>
                                <span class="bg-ucm-gold/20 text-ucm-red font-semibold px-4 py-1.5 rounded-full mr-3 mb-2">
                                    Status: PENDING REVIEW
                                </span>
                                <span class="bg-blue-100 text-blue-700 px-4 py-1.5 rounded-full mr-3 mb-2">
                                    Harmon College Specific
                                </span>
                            </div>
                        </div>
                        
                        <div class="bg-white p-6 rounded-2xl shadow-xl border border-gray-100 hover:shadow-2xl transition duration-200 cursor-pointer">
                            <div class="flex justify-between items-start">
                                <h3 class="text-2xl font-bold text-gray-900 hover:text-ucm-red transition-colors">
                                    <a href="#">Accountancy Scholarship Fund</a>
                                </h3>
                                <button class="text-gray-400 hover:text-ucm-red transition-colors" title="Save Opportunity">
                                    <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z"></path></svg>
                                </button>
                            </div>
                            
                            <p class="text-gray-600 mt-2 mb-4 text-lg">
                                The Department of Accountancy Scholarship is available through the UCM Alumni Foundation.
                            </p>
                            
                            <div class="flex flex-wrap items-center text-base">
                                <span class="bg-gray-100 text-gray-700 font-medium px-4 py-1.5 rounded-full mr-3 mb-2">
                                    Amount: $1,000
                                </span>
                                <span class="bg-ucm-gold/20 text-ucm-red font-semibold px-4 py-1.5 rounded-full mr-3 mb-2">
                                    Deadline: Mar 15, 2026
                                </span>
                                <span class="bg-ucm-red/10 text-ucm-red px-4 py-1.5 rounded-full mr-3 mb-2">
                                    Departmental
                                </span>
                            </div>
                        </div>
                        
                        <div class="flex justify-center pt-8">
                            <nav class="flex space-x-4 text-xl">
                                <button class="bg-white px-6 py-3 rounded-xl border-2 border-gray-300 text-gray-500 hover:bg-gray-100 transition-colors">Previous</button>
                                <span class="bg-ucm-red text-white px-6 py-3 rounded-xl font-bold">1</span>
                                <button class="bg-white px-6 py-3 rounded-xl border-2 border-gray-300 text-gray-700 hover:bg-gray-100 transition-colors">2</button>
                                <button class="bg-white px-6 py-3 rounded-xl border-2 border-gray-300 text-gray-700 hover:bg-gray-100 transition-colors">3</button>
                                <button class="bg-white px-6 py-3 rounded-xl border-2 border-gray-300 text-gray-500 hover:bg-gray-100 transition-colors">Next</button>
                            </nav>
                        </div>

                    </div>
                </section>
            </div>
        </main>

        <main id="view-results" class="hidden flex-grow w-full p-10 overflow-y-auto">
            <div class="space-y-10">
                
                <div class="bg-white p-8 rounded-2xl shadow-xl border-t-8 border-ucm-gold">
                    <h2 class="text-5xl font-extrabold text-gray-900 mb-4 flex items-center">
                        <svg class="w-12 h-12 text-ucm-red mr-4" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path></svg>
                        Your Scholarships Are Ready!
                    </h2>
                    <p class="text-2xl text-gray-600 mt-4">
                        Congratulations on completing the application process! Review the status of the specific scholarships you applied for below.
                    </p>
                </div>

                <div class="space-y-4 sm:space-y-6 grid grid-cols-1 sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-4 sm:gap-6">
                    <!-- Example Opportunity Card -->
                    <div class="bg-white p-4 sm:p-6 rounded-2xl shadow-xl border border-gray-100 hover:shadow-2xl transition duration-200 cursor-pointer" onclick="openModal()">
                <section class="space-y-6">
                    <h3 class="text-3xl font-bold text-gray-900 border-b pb-3">Application Results</h3>
                    
                    <div class="bg-white p-8 rounded-2xl shadow-2xl border-l-8 border-green-600">
                        <div class="flex justify-between items-start">
                            <h3 class="text-lg sm:text-2xl font-bold text-gray-900 hover:text-ucm-red transition-colors">
                                <a href="#" onclick="event.preventDefault(); event.stopPropagation();">A. Ralph Boxell Eagle Scout Scholarship</a>
                            </h3>
                            <button class="text-gray-400 hover:text-ucm-red transition-colors" title="Save Opportunity" onclick="event.stopPropagation()">
                                <svg class="w-5 h-5 sm:w-8 sm:h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z"></path></svg>
                            </button>
                            <h4 class="text-3xl font-bold text-green-700">
                                <span class="bg-green-100 text-green-700 px-4 py-2 rounded-full mr-4 text-xl font-extrabold">AWARDED</span>
                                UCM Presidential Leadership Scholarship
                            </h4>
                            <span class="text-4xl font-extrabold text-green-600">$5,000</span>
                        </div>
                        <p class="text-sm sm:text-lg text-gray-600 mt-2 mb-2 sm:mb-4">
                            Available through the UCM Alumni Foundation for active Eagle Scouts enrolled at UCM.
                        
                        <p class="text-gray-700 mt-4 mb-6 text-xl leading-relaxed">
                            Congratulations! You have been selected to receive the Presidential Leadership Scholarship for the 2026-2027 academic year. Please check your official UCM email for the next steps and acceptance form required to claim these funds.
                        </p>
                        <div class="flex flex-wrap items-center text-xs sm:text-base">
                            <span class="bg-gray-100 text-gray-700 font-medium px-2 sm:px-4 py-1 rounded-full mr-2 mb-2">Amount: Varies</span>
                            <span class="bg-ucm-gold/20 text-ucm-red font-semibold px-2 sm:px-4 py-1 rounded-full mr-2 mb-2">Deadline: Mar 15, 2026</span>
                            <span class="bg-ucm-red/10 text-ucm-red px-2 sm:px-4 py-1 rounded-full mr-2 mb-2">General Application</span>
                        
                        <div class="flex items-center space-x-4 pt-4 border-t border-green-100">
                            <span class="text-lg font-medium text-gray-500">
                                Status: Accepted on Oct 21, 2025
                            </span>
                            <button class="bg-green-600 text-white font-semibold py-2 px-6 rounded-xl text-xl hover:bg-green-700 transition duration-200">
                                View Acceptance Form
                            </button>
                        </div>
                    </div>
                    <!-- Repeat other opportunity cards here... -->
                </div>
            </section>
        </main>

        <!-- Results View -->
        <main id="view-results" class="hidden flex-grow w-full p-4 sm:p-6 md:p-10 overflow-y-auto space-y-10">
            <!-- Similar responsive adjustments applied to My Decisions section -->
                    <div class="bg-white p-8 rounded-2xl shadow-2xl border-l-8 border-gray-400">
                        <div class="flex justify-between items-start">
                            <h4 class="text-3xl font-bold text-gray-700">
                                <span class="bg-gray-200 text-gray-700 px-4 py-2 rounded-full mr-4 text-xl font-extrabold">NOT AWARDED</span>
                                Department of Computer Science Dean's Award
                            </h4>
                            <span class="text-4xl font-extrabold text-gray-500">30,000</span>
                        </div>
                        
                        <p class="text-gray-700 mt-4 mb-6 text-xl leading-relaxed">
                            Thank you for your application. Due to the highly competitive nature of this award and the limited funds available, we regret to inform you that you were not selected for the Computer Science Dean's Award this cycle. We encourage you to review other opportunities on the Search page.
                        </p>
                        
                        <div class="flex items-center space-x-4 pt-4 border-t border-gray-200">
                            <span class="text-lg font-medium text-gray-500">
                                Status: Decision Finalized
                            </span>
                            <button class="bg-ucm-red text-white font-semibold py-2 px-6 rounded-xl text-xl opacity-50 cursor-not-allowed">
                                View Details (Closed)
                            </button>
                        </div>
                    </div>
                </section>
                
            </div>
        </main>

        <!-- Footer -->
        <footer class="bg-gray-800 text-white flex-shrink-0 py-4 px-4 sm:px-10 text-center text-sm sm:text-lg">
        <footer class="bg-gray-800 text-white flex-shrink-0 py-4 px-10 text-center text-lg">
            <p class="text-gray-400">&copy; 2025 University of Central Missouri. Financial Aid & Scholarship Office.</p>
        </footer>
    </div>
    <div id="detail-modal" class="hidden fixed inset-0 bg-gray-900 bg-opacity-75 z-50 flex justify-center items-center p-4" onclick="closeModal()">
        
        <div class="bg-white w-full max-w-5xl max-h-[90vh] rounded-2xl shadow-2xl transform transition-all overflow-y-auto text-2xl" onclick="event.stopPropagation()">
            
            <div class="sticky top-0 bg-white p-8 border-b flex justify-between items-start z-10">
                <h2 class="text-4xl font-extrabold text-ucm-red">A. Ralph Boxell Eagle Scout Scholarship</h2>
                <button onclick="closeModal()" class="text-gray-400 hover:text-gray-800 transition-colors p-2 rounded-full">
                    <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
                </button>
            </div>

    <!-- Modal -->
    <div id="detail-modal" class="hidden fixed inset-0 bg-gray-900 bg-opacity-75 z-50 flex justify-center items-center p-2 sm:p-4" onclick="closeModal()">
        <div class="bg-white w-full max-w-lg sm:max-w-3xl max-h-[90vh] rounded-2xl shadow-2xl overflow-y-auto text-base sm:text-2xl" onclick="event.stopPropagation()">
            <!-- Modal content same as before, now responsive -->
            <div class="p-8 space-y-8">
                
                <div class="grid grid-cols-1 sm:grid-cols-3 gap-6 border-b pb-6">
                    <div class="flex flex-col">
                        <span class="text-base font-semibold uppercase text-gray-500">Award Amount</span>
                        <span class="text-3xl font-bold text-gray-800">Varies</span>
                    </div>
                    <div class="flex flex-col">
                        <span class="text-base font-semibold uppercase text-gray-500">Deadline</span>
                        <span class="text-3xl font-bold text-ucm-red">Mar 15, 2026</span>
                    </div>
                    <div class="flex flex-col">
                        <span class="text-base font-semibold uppercase text-gray-500">Department</span>
                        <span class="text-3xl font-bold text-gray-800">Alumni Foundation</span>
                    </div>
                </div>

                <div>
                    <h3 class="text-3xl font-bold text-gray-900 mb-4">Description</h3>
                    <p class="text-gray-700 leading-relaxed">
                        This scholarship was established through the generous donation of the Boxell family to support students demonstrating exceptional dedication to leadership, service, and community involvement. Preference is given to active Eagle Scouts enrolled at the University of Central Missouri. All applicants must meet the general requirements for institutional aid, maintain a minimum 3.0 GPA, and be enrolled full-time (at least 12 credit hours). Funds are disbursed equally across the Fall and Spring semesters.
                    </p>
                </div>
                
                <div>
                    <h3 class="text-3xl font-bold text-gray-900 mb-4">Eligibility Requirements</h3>
                    <ul class="list-disc list-inside space-y-2 text-gray-700 pl-4">
                        <li>Must be an active, enrolled student at UCM.</li>
                        <li>Must maintain a cumulative GPA of 3.5 or higher.</li>
                        <li>Must be enrolled in a minimum of 12 credit hours per semester.</li>
                        <li>Must submit documentation verifying Eagle Scout status.</li>
                        <li>Financial need may be considered but is not mandatory.</li>
                    </ul>
                </div>

                <div class="pt-6 border-t">
                    <button class="w-full bg-ucm-red text-white font-extrabold py-4 rounded-xl shadow-lg hover:bg-ucm-red/90 transition-opacity text-2xl focus:outline-none focus:ring-4 focus:ring-ucm-red/50">
                        Apply Now
                    </button>
                </div>

            </div>
        </div>
    </div>

</body>
</html>
