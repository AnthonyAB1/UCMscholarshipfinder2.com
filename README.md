<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UCM Scholarship Portal - Home/Search</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
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
         * Function to switch between the main application views (Home/Search, Decisions, and General Application).
         * @param {string} viewId - The ID of the view to display.
         */
        function switchView(viewId) {
            // Define all main views
            const views = ['view-home', 'view-results', 'view-general-application'];
            
            // Hide all views
            views.forEach(id => {
                const element = document.getElementById(id);
                if (element) {
                    element.classList.add('hidden');
                }
            });

            // Show the requested view
            const newView = document.getElementById(viewId);
            if (newView) {
                newView.classList.remove('hidden');
                // Ensure the view scrolls to the top when switched
                newView.scrollTop = 0;

                // Simple navigation button highlighting logic
                const isHome = viewId === 'view-home';
                const isResults = viewId === 'view-results';
                const isApp = viewId === 'view-general-application';

                // Home Button
                document.getElementById('nav-home').classList.toggle('bg-ucm-gold', isHome);
                document.getElementById('nav-home').classList.toggle('bg-white', !isHome);
                document.getElementById('nav-home').classList.toggle('text-ucm-red', isHome);
                document.getElementById('nav-home').classList.toggle('text-gray-700', !isHome);
                document.getElementById('nav-home').classList.toggle('border-ucm-red', !isHome);
                document.getElementById('nav-home').classList.toggle('border-transparent', isHome);


                // Results Button
                document.getElementById('nav-results').classList.toggle('bg-white', isHome || isApp);
                document.getElementById('nav-results').classList.toggle('bg-ucm-gold', isResults);
                document.getElementById('nav-results').classList.toggle('text-gray-700', isHome || isApp);
                document.getElementById('nav-results').classList.toggle('text-ucm-red', isResults);
                document.getElementById('nav-results').classList.toggle('border-ucm-red', isHome || isApp);
                document.getElementById('nav-results').classList.toggle('border-transparent', isResults);


                // General Application Button (For easy testing, can be hidden in production)
                // Note: The main CTA for this is on the Home page, but this button is here for completeness.
                document.getElementById('nav-app').classList.toggle('bg-white', isHome || isResults);
                document.getElementById('nav-app').classList.toggle('bg-ucm-gold', isApp);
                document.getElementById('nav-app').classList.toggle('text-gray-700', isHome || isResults);
                document.getElementById('nav-app').classList.toggle('text-ucm-red', isApp);
                document.getElementById('nav-app').classList.toggle('border-ucm-red', isHome || isResults);
                document.getElementById('nav-app').classList.toggle('border-transparent', isApp);
            }
        }

        // JavaScript for Modal Functionality
        function openModal() {
            const modal = document.getElementById('detail-modal');
            if (modal) {
                modal.classList.remove('hidden');
            }
        }

        function closeModal() {
            const modal = document.getElementById('detail-modal');
            if (modal) {
                modal.classList.add('hidden');
            }
        }
        
        // Initial view load function (set the home view as default on load)
        document.addEventListener('DOMContentLoaded', () => {
            switchView('view-home');
            // Attach event listener to the General Application CTA on the home screen
            document.getElementById('cta-general-application').addEventListener('click', (e) => {
                e.preventDefault();
                switchView('view-general-application');
            });
        });
    </script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #e5e7eb; /* Background for the surrounding viewport */
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: flex-start; /* Start from the top */
            padding-top: 20px;
        }

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
        /* Custom select arrow styling */
        select {
            background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 20 20' fill='none'%3e%3cpath fill='%23990000' d='M7 9l3 3 3-3'/%3e%3c/svg%3e");
            background-repeat: no-repeat;
            background-position: right 1rem center;
            background-size: 1.5em;
            padding-right: 3rem !important;
        }
    </style>
</head>
<body class="antialiased text-gray-800">

    <div id="template-container" class="bg-ucm-surface">

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

                <nav class="flex items-center space-x-6">
                    <button id="nav-home" onclick="switchView('view-home')" class="bg-ucm-gold text-ucm-red font-semibold py-3 px-8 text-xl rounded-xl shadow-md hover:opacity-90 transition duration-300 border border-transparent">
                        Scholarship Search
                    </button>
                    <button id="nav-app" onclick="switchView('view-general-application')" class="bg-white text-gray-700 font-semibold py-3 px-8 text-xl rounded-xl shadow-md hover:bg-gray-100 transition duration-300 border border-ucm-red">
                        General Application
                    </button>
                    <button id="nav-results" onclick="switchView('view-results')" class="bg-white text-gray-700 font-semibold py-3 px-8 text-xl rounded-xl shadow-md hover:bg-gray-100 transition duration-300 border border-ucm-red">
                        My Decisions
                    </button>
                    <button class="p-3 text-white rounded-full hover:bg-white/20 transition-colors">
                        <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                    </button>
                </nav>
            </div>
        </header>

        <main id="view-home" class="flex-grow w-full p-10 overflow-y-auto">
            <div class="space-y-8">

                <section class="bg-white p-10 rounded-2xl shadow-xl border-t-8 border-ucm-red flex-shrink-0">
                    <h2 class="text-4xl font-extrabold text-gray-900 mb-3 flex items-center">
                        <svg class="w-10 h-10 text-ucm-gold mr-4" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M5 4a2 2 0 012-2h6a2 2 0 012 2v14l-5-2.5L5 18V4z"></path></svg>
                        Find Your Funding
                    </h2>
                    <p class="text-xl text-gray-600 mb-6">
                        Welcome to the UCM Scholarship Portal! Use the tools below to explore all available scholarship opportunities, grants, and awards. Be sure to complete the General Application to be matched with dozens of awards automatically.
                    </p>
                    <a id="cta-general-application" href="#" onclick="event.preventDefault()" class="inline-block bg-ucm-gold text-ucm-red font-extrabold py-3 px-8 text-xl rounded-xl shadow-lg hover:bg-opacity-80 transition duration-300">
                        Complete General Application &rarr;
                    </a>
                </section>
                
                <aside class="bg-white p-8 rounded-2xl shadow-xl border border-gray-100 flex-shrink-0">
                    <h2 class="text-3xl font-bold text-gray-900 mb-6 border-b pb-3">Filter Opportunities</h2>
                    
                    <div class="mb-6">
                        <label for="keyword-search" class="block text-lg font-medium text-gray-700 mb-2">Search by Keyword</label>
                        <input type="text" id="keyword-search" placeholder="e.g., Biology, Leadership" class="w-full p-4 text-xl border-2 border-gray-300 rounded-xl focus:ring-ucm-red focus:border-ucm-red transition-shadow">
                    </div>

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
                        </div>

                        <div>
                            <h3 class="text-lg font-medium text-gray-700 mb-2">Award Type</h3>
                            <div class="grid grid-cols-2 gap-3">
                                <label class="flex items-center text-base text-gray-600">
                                    <input type="checkbox" class="h-6 w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red" checked>
                                    <span class="ml-2">Scholarship (40)</span>
                                </label>
                                <label class="flex items-center text-base text-gray-600">
                                    <input type="checkbox" class="h-6 w-6 text-ucm-red border-gray-300
