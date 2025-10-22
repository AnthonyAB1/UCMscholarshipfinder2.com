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
         * Function to switch between the main application views (Home/Search and Decisions).
         * @param {string} viewId - The ID of the view to display ('view-home' or 'view-results').
         */
        function switchView(viewId) {
            // Update view IDs from 'view-search' to 'view-home'
            const views = ['view-home', 'view-results']; 
            views.forEach(id => {
                const element = document.getElementById(id);
                if (element) {
                    element.classList.add('hidden');
                }
            });

            const newView = document.getElementById(viewId);
            if (newView) {
                newView.classList.remove('hidden');
                // Ensure the view scrolls to the top when switched
                newView.scrollTop = 0;

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
        });
    </script>
    <style>
    body {
    font-family: 'Inter', sans-serif;
    background-color: #e5e7eb;
    min-height: 100vh;       /* ensures body covers at least full viewport */
    margin: 0;               /* remove default body margin */
    padding-top: 20px;       /* optional spacing at top */
    overflow-x: hidden;      /* prevents horizontal scroll */
}

/* Make the template container responsive and scrollable */
#template-container {
    width: 100%;
    max-width: 1080px;       /* Desktop max width */
    margin: 0 auto;
    box-shadow: 0 15px 50px rgba(0,0,0,0.2);
    display: flex;
    flex-direction: column;
    border-radius: 12px;
    overflow: visible;       /* let content flow naturally */
}

/* Make header sticky */
header {
    position: sticky;
    top: 0;
    z-index: 50;             /* above main content */
}

/* Header, main, footer adapt to container width */
header, main, footer {
    width: 100%;
    box-sizing: border-box;
}

/* Optional: custom scrollbar for main */
main::-webkit-scrollbar {
    width: 8px;
}
main::-webkit-scrollbar-track {
    background: #e5e7eb;
}
main::-webkit-scrollbar-thumb {
    background-color: #d1d5db;
    border-radius: 20px;
    border: 2px solid #e5e7eb;
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

        <main id="view-home" class="flex-grow w-full p-10 overflow-y-auto">
            <div class="space-y-8">

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
                    
                    <button class="w-full bg-ucm-red text-white font-extrabold text-xl py-3 rounded-xl shadow-lg hover:opacity-90 transition-opacity">
                        Apply Filters
                    </button>
                </aside>

                ---

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

                <section class="space-y-6">
                    <h3 class="text-3xl font-bold text-gray-900 border-b pb-3">Application Results</h3>
                    
                    <div class="bg-white p-8 rounded-2xl shadow-2xl border-l-8 border-green-600">
                        <div class="flex justify-between items-start">
                            <h4 class="text-3xl font-bold text-green-700">
                                <span class="bg-green-100 text-green-700 px-4 py-2 rounded-full mr-4 text-xl font-extrabold">AWARDED</span>
                                UCM Presidential Leadership Scholarship
                            </h4>
                            <span class="text-4xl font-extrabold text-green-600">$5,000</span>
                        </div>
                        
                        <p class="text-gray-700 mt-4 mb-6 text-xl leading-relaxed">
                            Congratulations! You have been selected to receive the Presidential Leadership Scholarship for the 2026-2027 academic year. Please check your official UCM email for the next steps and acceptance form required to claim these funds.
                        </p>
                        
                        <div class="flex items-center space-x-4 pt-4 border-t border-green-100">
                            <span class="text-lg font-medium text-gray-500">
                                Status: Accepted on Oct 21, 2025
                            </span>
                            <button class="bg-green-600 text-white font-semibold py-2 px-6 rounded-xl text-xl hover:bg-green-700 transition duration-200">
                                View Acceptance Form
                            </button>
                        </div>
                    </div>

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
