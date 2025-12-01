
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>UCM Scholarship Portal - Home/Search</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>
<script>
   // Custom Tailwind Configuration
@@ -28,8 +29,12 @@
    * @param {string} viewId - The ID of the view to display ('view-home' or 'view-results').
    */
   function switchView(viewId) {
            // Update view IDs from 'view-search' to 'view-home'
       const views = ['view-home', 'view-results']; 
            const navElements = {
                'view-home': document.getElementById('nav-home'),
                'view-results': document.getElementById('nav-results')
            };

       views.forEach(id => {
           const element = document.getElementById(id);
           if (element) {
@@ -44,14 +49,19 @@
           newView.scrollTop = 0;

           // Simple navigation button highlighting logic
                document.getElementById('nav-home').classList.toggle('bg-ucm-gold', viewId === 'view-home');
                document.getElementById('nav-home').classList.toggle('bg-white', viewId !== 'view-home');
                document.getElementById('nav-results').classList.toggle('bg-white', viewId === 'view-home');
                document.getElementById('nav-results').classList.toggle('bg-ucm-gold', viewId !== 'view-home');

                // Swap text colors based on selected view
                document.getElementById('nav-home').classList.toggle('text-ucm-red', viewId === 'view-home');
                document.getElementById('nav-results').classList.toggle('text-ucm-red', viewId !== 'view-home');
                Object.keys(navElements).forEach(id => {
                    const isSelected = id === viewId;
                    const navButton = navElements[id];
                    
                    navButton.classList.toggle('bg-ucm-gold', isSelected);
                    navButton.classList.toggle('bg-white', !isSelected);
                    navButton.classList.toggle('text-ucm-red', isSelected);
                    navButton.classList.toggle('text-ucm-red', !isSelected); // Keep text red on both for clear contrast
                    navButton.classList.toggle('font-extrabold', isSelected); // Enhance selected button
                    navButton.classList.toggle('font-semibold', !isSelected);
                    navButton.classList.toggle('border-ucm-red', !isSelected);
                    navButton.classList.toggle('border-transparent', isSelected);
                });
       }
   }

@@ -117,6 +127,14 @@

<div id="template-container" class="bg-ucm-surface">

        <div class="flex-shrink-0 w-full h-12 bg-ucm-red text-white flex justify-between items-center px-6 text-xl font-medium">
            <span>9:16</span>
            <div class="flex items-center space-x-2">
                <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M12 4.07V2.5A1.5 1.5 0 0113.5 1h-3A1.5 1.5 0 019 2.5v1.57A8 8 0 1012 20a8 8 0 000-15.93zM12 18a6 6 0 110-12 6 6 0 010 12z"></path></svg>
                <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M19 12h-2V6h-4V4h4V2h2v2h2v2h-2v6zM4 18h16v-2H4v2zm0-4h16v-2H4v2z"></path></svg>
                <svg class="w-8 h-8" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M17 5v14c0 1.1-.9 2-2 2H9c-1.1 0-2-.9-2-2V5c0-1.1.9-2 2-2h6c1.1 0 2 .9 2 2zM9 5h6v14H9V5z"></path></svg>
            </div>
        </div>
   <header class="bg-ucm-red shadow-lg flex-shrink-0 h-32 px-10 py-6">
       <div class="flex justify-between items-center h-full">
           <div class="flex items-center space-x-5 cursor-pointer" onclick="switchView('view-home')">
@@ -129,13 +147,13 @@
           </div>

           <nav class="flex items-center space-x-6">
                    <button id="nav-home" onclick="switchView('view-home')" class="bg-ucm-gold text-ucm-red font-semibold py-3 px-8 text-xl rounded-xl shadow-md hover:opacity-90 transition duration-300">
                    <button id="nav-home" onclick="switchView('view-home')" class="bg-ucm-gold text-ucm-red font-extrabold py-3 px-8 text-xl rounded-xl shadow-md hover:opacity-90 transition duration-300 border-transparent">
                   Scholarship Search
               </button>
                    <button id="nav-results" onclick="switchView('view-results')" class="bg-white text-ucm-red font-semibold py-3 px-8 text-xl rounded-xl shadow-md hover:bg-gray-100 transition duration-300 border border-ucm-red">
                    <button id="nav-results" onclick="switchView('view-results')" class="bg-white text-ucm-red font-semibold py-3 px-8 text-xl rounded-xl shadow-md hover:bg-gray-100 transition duration-300 border-2 border-ucm-red">
                   My Decisions
               </button>
                    <button class="p-3 text-white rounded-full hover:bg-white/20 transition-colors">
                    <button class="p-3 text-white rounded-full hover:bg-white/20 transition-colors" title="Help & Information">
                   <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
               </button>
           </nav>
@@ -171,13 +189,18 @@
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
                            <div class="relative">
                                <select id="department-filter" class="w-full p-4 text-xl border-2 border-gray-300 rounded-xl bg-white focus:ring-ucm-red focus:border-ucm-red transition-shadow appearance-none">
                                    <option>All Departments (54)</option>
                                    <option>College of Arts, Humanities...</option>
                                    <option>Harmon College of Business (12)</option>
                                    <option>Department of Agriculture (4)</option>
                                    <option>School of Nursing (8)</option>
                                </select>
                                <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-4 text-gray-700">
                                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                                </div>
                            </div>
                   </div>

                   <div>
@@ -215,21 +238,26 @@
                   <h2 class="text-3xl font-bold text-gray-900">Opportunities <span class="text-xl font-normal text-gray-500">(54 Total)</span></h2>
                   <div class="flex items-center space-x-3">
                       <label for="sort-by" class="text-lg text-gray-600 font-medium">Sort:</label>
                            <select id="sort-by" class="p-2 text-lg border border-gray-300 rounded-xl">
                                <option>Deadline (Earliest)</option>
                                <option>Award Amount (High to Low)</option>
                                <option>Alphabetical (A-Z)</option>
                            </select>
                            <div class="relative">
                                <select id="sort-by" class="p-3 text-lg border border-gray-300 rounded-xl bg-white appearance-none">
                                    <option>Deadline (Earliest)</option>
                                    <option>Award Amount (High to Low)</option>
                                    <option>Alphabetical (A-Z)</option>
                                </select>
                                <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-3 text-gray-700">
                                    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                                </div>
                            </div>
                   </div>
               </div>

               <div class="space-y-6">
                   <div class="bg-white p-6 rounded-2xl shadow-xl border border-gray-100 hover:shadow-2xl transition duration-200 cursor-pointer" onclick="openModal()">
                       <div class="flex justify-between items-start">
                           <h3 class="text-2xl font-bold text-gray-900 hover:text-ucm-red transition-colors">
                                    <a href="#" onclick="event.preventDefault();">A. Ralph Boxell Eagle Scout Scholarship</a>
                                    <a href="#" onclick="event.preventDefault(); event.stopPropagation();">A. Ralph Boxell Eagle Scout Scholarship</a>
                           </h3>
                                <button class="text-gray-400 hover:text-ucm-red transition-colors" title="Save Opportunity">
                                <button class="text-gray-400 hover:text-ucm-red transition-colors" title="Save Opportunity" onclick="event.stopPropagation()">
                               <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z"></path></svg>
                           </button>
                       </div>
@@ -251,12 +279,12 @@
                       </div>
                   </div>
                   
                        <div class="bg-white p-6 rounded-2xl shadow-xl border border-gray-100 hover:shadow-2xl transition duration-200 cursor-pointer">
                        <div class="bg-white p-6 rounded-2xl shadow-xl border border-gray-100 hover:shadow-2xl transition duration-200 cursor-pointer" onclick="openModal()">
                       <div class="flex justify-between items-start">
                           <h3 class="text-2xl font-bold text-gray-900 hover:text-ucm-red transition-colors">
                                    <a href="#">Harmon College Business Graduate Scholarship</a>
                                    <a href="#" onclick="event.preventDefault(); event.stopPropagation();">Harmon College Business Graduate Scholarship</a>
                           </h3>
                                <button class="text-ucm-red transition-colors" title="Remove from Saved">
                                <button class="text-ucm-red transition-colors" title="Remove from Saved" onclick="event.stopPropagation()">
                               <svg class="w-8 h-8" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z"></path></svg>
                           </button>
                       </div>
@@ -269,21 +297,21 @@
                           <span class="bg-gray-100 text-gray-700 font-medium px-4 py-1.5 rounded-full mr-3 mb-2">
                               Amount: Full Ride
                           </span>
                                <span class="bg-ucm-gold/20 text-ucm-red font-semibold px-4 py-1.5 rounded-full mr-3 mb-2">
                                    Status: PENDING REVIEW
                                <span class="bg-yellow-100 text-yellow-800 font-semibold px-4 py-1.5 rounded-full mr-3 mb-2">
                                    Status: APPLICATION IN PROGRESS
                           </span>
                           <span class="bg-blue-100 text-blue-700 px-4 py-1.5 rounded-full mr-3 mb-2">
                               Harmon College Specific
                           </span>
                       </div>
                   </div>
                   
                        <div class="bg-white p-6 rounded-2xl shadow-xl border border-gray-100 hover:shadow-2xl transition duration-200 cursor-pointer">
                        <div class="bg-white p-6 rounded-2xl shadow-xl border border-gray-100 hover:shadow-2xl transition duration-200 cursor-pointer" onclick="openModal()">
                       <div class="flex justify-between items-start">
                           <h3 class="text-2xl font-bold text-gray-900 hover:text-ucm-red transition-colors">
                                    <a href="#">Accountancy Scholarship Fund</a>
                                    <a href="#" onclick="event.preventDefault(); event.stopPropagation();">Accountancy Scholarship Fund</a>
                           </h3>
                                <button class="text-gray-400 hover:text-ucm-red transition-colors" title="Save Opportunity">
                                <button class="text-gray-400 hover:text-ucm-red transition-colors" title="Save Opportunity" onclick="event.stopPropagation()">
                               <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z"></path></svg>
                           </button>
                       </div>
@@ -307,11 +335,11 @@
                   
                   <div class="flex justify-center pt-8">
                       <nav class="flex space-x-4 text-xl">
                                <button class="bg-white px-6 py-3 rounded-xl border-2 border-gray-300 text-gray-500 hover:bg-gray-100 transition-colors">Previous</button>
                                <span class="bg-ucm-red text-white px-6 py-3 rounded-xl font-bold">1</span>
                                <button class="bg-white px-6 py-3 rounded-xl border-2 border-gray-300 text-gray-700 hover:bg-gray-100 transition-colors">2</button>
                                <button class="bg-white px-6 py-3 rounded-xl border-2 border-gray-300 text-gray-700 hover:bg-gray-100 transition-colors">3</button>
                                <button class="bg-white px-6 py-3 rounded-xl border-2 border-gray-300 text-gray-500 hover:bg-gray-100 transition-colors">Next</button>
                                <button class="bg-white px-6 py-3 rounded-xl border-2 border-gray-300 text-gray-500 hover:bg-gray-100 transition-colors cursor-not-allowed">Previous</button>
                                <span class="bg-ucm-red text-white px-6 py-3 rounded-xl font-bold shadow-md">1</span>
                                <button class="bg-white px-6 py-3 rounded-xl border-2 border-gray-300 text-gray-700 hover:bg-gray-100 transition-colors shadow-sm">2</button>
                                <button class="bg-white px-6 py-3 rounded-xl border-2 border-gray-300 text-gray-700 hover:bg-gray-100 transition-colors shadow-sm">3</button>
                                <button class="bg-white px-6 py-3 rounded-xl border-2 border-gray-300 text-gray-700 hover:bg-gray-100 transition-colors shadow-sm">Next</button>
                       </nav>
                   </div>

@@ -326,7 +354,7 @@
           <div class="bg-white p-8 rounded-2xl shadow-xl border-t-8 border-ucm-gold">
               <h2 class="text-5xl font-extrabold text-gray-900 mb-4 flex items-center">
                   <svg class="w-12 h-12 text-ucm-red mr-4" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path></svg>
                        Your Scholarships Are Ready!
                        Your Decisions Are Ready!
               </h2>
               <p class="text-2xl text-gray-600 mt-4">
                   Congratulations on completing the application process! Review the status of the specific scholarships you applied for below.
@@ -353,7 +381,7 @@
                       <span class="text-lg font-medium text-gray-500">
                           Status: Accepted on Oct 21, 2025
                       </span>
                            <button class="bg-green-600 text-white font-semibold py-2 px-6 rounded-xl text-xl hover:bg-green-700 transition duration-200">
                            <button class="bg-green-600 text-white font-semibold py-2 px-6 rounded-xl text-xl hover:bg-green-700 transition duration-200 shadow-md">
                           View Acceptance Form
                       </button>
                   </div>
@@ -365,8 +393,7 @@
                           <span class="bg-gray-200 text-gray-700 px-4 py-2 rounded-full mr-4 text-xl font-extrabold">NOT AWARDED</span>
                           Department of Computer Science Dean's Award
                       </h4>
                            <span class="text-4xl font-extrabold text-gray-500">30,000</span>
                        </div>
                            <span class="text-4xl font-extrabold text-gray-500">$3,000</span> </div>
                   
                   <p class="text-gray-700 mt-4 mb-6 text-xl leading-relaxed">
                       Thank you for your application. Due to the highly competitive nature of this award and the limited funds available, we regret to inform you that you were not selected for the Computer Science Dean's Award this cycle. We encourage you to review other opportunities on the Search page.
@@ -376,7 +403,7 @@
                       <span class="text-lg font-medium text-gray-500">
                           Status: Decision Finalized
                       </span>
                            <button class="bg-ucm-red text-white font-semibold py-2 px-6 rounded-xl text-xl opacity-50 cursor-not-allowed">
                            <button class="bg-ucm-red text-white font-semibold py-2 px-6 rounded-xl text-xl opacity-50 cursor-not-allowed shadow-md">
                           View Details (Closed)
                       </button>
                   </div>
@@ -385,17 +412,19 @@
           
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
                <button onclick="closeModal()" class="text-gray-400 hover:text-gray-800 transition-colors p-2 rounded-full" title="Close">
               <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
           </button>
       </div>
@@ -428,7 +457,7 @@
               <h3 class="text-3xl font-bold text-gray-900 mb-4">Eligibility Requirements</h3>
               <ul class="list-disc list-inside space-y-2 text-gray-700 pl-4">
                   <li>Must be an active, enrolled student at UCM.</li>
                        <li>Must maintain a cumulative GPA of 3.5 or higher.</li>
                        <li>Must maintain a cumulative GPA of **3.5 or higher**.</li>
                   <li>Must be enrolled in a minimum of 12 credit hours per semester.</li>
                   <li>Must submit documentation verifying Eagle Scout status.</li>
                   <li>Financial need may be considered but is not mandatory.</li>
