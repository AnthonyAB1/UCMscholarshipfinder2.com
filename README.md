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
    },
  },
};

/**
 * Function to switch between the main application views (Home/Search and Decisions).
 */
function switchView(viewId) {
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
    newView.scrollTop = 0;

    document.getElementById('nav-home').classList.toggle('bg-ucm-gold', viewId === 'view-home');
    document.getElementById('nav-home').classList.toggle('bg-white', viewId !== 'view-home');
    document.getElementById('nav-results').classList.toggle('bg-white', viewId === 'view-home');
    document.getElementById('nav-results').classList.toggle('bg-ucm-gold', viewId !== 'view-home');
    document.getElementById('nav-home').classList.toggle('text-ucm-red', viewId === 'view-home');
    document.getElementById('nav-results').classList.toggle('text-ucm-red', viewId !== 'view-home');
  }
}

// JavaScript for Modal Functionality
function openModal() {
  const modal = document.getElementById('detail-modal');
  if (modal) modal.classList.remove('hidden');
}

function closeModal() {
  const modal = document.getElementById('detail-modal');
  if (modal) modal.classList.add('hidden');
}

// Load default view
document.addEventListener('DOMContentLoaded', () => {
  switchView('view-home');
});
</script>

<style>
body {
  font-family: 'Inter', sans-serif;
  background-color: #e5e7eb;
  min-height: 100vh;
  margin: 0;
  padding: 20px 0;
  display: flex;
  justify-content: center;
  overflow-x: hidden;
}

#template-container {
  width: 95%;
  max-width: 1080px;
  margin: 0 auto;
  box-shadow: 0 15px 50px rgba(0,0,0,0.2);
  display: flex;
  flex-direction: column;
  border-radius: 12px;
  overflow: visible;
}

header {
  position: sticky;
  top: 0;
  z-index: 50;
}

header, main, footer {
  width: 100%;
  box-sizing: border-box;
}

main {
  overflow-y: auto;
  max-height: calc(100vh - 140px);
}

/* Scrollbar styling */
main::-webkit-scrollbar { width: 6px; }
main::-webkit-scrollbar-track { background: #e5e7eb; }
main::-webkit-scrollbar-thumb {
  background-color: #d1d5db;
  border-radius: 20px;
  border: 2px solid #e5e7eb;
}

/* Responsive adjustments */
@media (max-width: 640px) {
  #template-container {
    width: 95%;
    padding: 0 10px;
  }
  header h1 {
    font-size: 2xl;
  }
  button {
    padding: 2px 6px;
    font-size: 0.9rem;
  }
}
</style>
</head>

<body>

<div id="template-container" class="bg-ucm-surface">

<header class="bg-ucm-red shadow-lg flex-shrink-0 h-32 px-10 py-6">
  <div class="flex justify-between items-center h-full">
    <div class="flex items-center space-x-5 cursor-pointer" onclick="switchView('view-home')">
      <div class="w-16 h-16 bg-white rounded-full flex items-center justify-center text-ucm-red font-extrabold text-3xl">UCM</div>
      <h1 class="text-4xl font-bold text-white tracking-wide">Scholarship Portal</h1>
    </div>

    <nav class="flex items-center space-x-6">
      <button id="nav-home" onclick="switchView('view-home')" class="bg-ucm-gold text-ucm-red font-semibold py-3 px-8 text-xl rounded-xl shadow-md hover:opacity-90 transition duration-300">Scholarship Search</button>
      <button id="nav-results" onclick="switchView('view-results')" class="bg-white text-ucm-red font-semibold py-3 px-8 text-xl rounded-xl shadow-md hover:bg-gray-100 transition duration-300 border border-ucm-red">My Decisions</button>
      <button class="p-3 text-white rounded-full hover:bg-white/20 transition-colors">
        <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
      </button>
    </nav>
  </div>
</header>

<!-- HOME VIEW -->
<main id="view-home" class="flex-grow w-full p-10 overflow-y-auto">
  <div class="space-y-8">
    <section class="bg-white p-10 rounded-2xl shadow-xl border-t-8 border-ucm-red flex-shrink-0">
      <h2 class="text-4xl font-extrabold text-gray-900 mb-3 flex items-center">
        <svg class="w-10 h-10 text-ucm-gold mr-4" fill="currentColor" viewBox="0 0 20 20"><path d="M5 4a2 2 0 012-2h6a2 2 0 012 2v14l-5-2.5L5 18V4z"></path></svg>
        Find Your Funding
      </h2>
      <p class="text-xl text-gray-600 mb-6">
        Welcome to the <strong>UCM Scholarship Portal</strong>! Use the tools below to explore all available scholarship opportunities, grants, and awards.
      </p>
      <a href="#" class="inline-block bg-ucm-gold text-ucm-red font-extrabold py-3 px-8 text-xl rounded-xl shadow-lg hover:bg-opacity-80 transition duration-300">
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
            <label class="flex items-center text-base text-gray-600"><input type="checkbox" class="h-6 w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red" checked><span class="ml-2">Scholarship (40)</span></label>
            <label class="flex items-center text-base text-gray-600"><input type="checkbox" class="h-6 w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red"><span class="ml-2">Grant (8)</span></label>
            <label class="flex items-center text-base text-gray-600"><input type="checkbox" class="h-6 w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red"><span class="ml-2">Award/Prize (6)</span></label>
            <label class="flex items-center text-base text-gray-600"><input type="checkbox" class="h-6 w-6 text-ucm-red border-gray-300 rounded focus:ring-ucm-red"><span class="ml-2">Pending (2)</span></label>
          </div>
        </div>
      </div>

      <button class="w-full bg-ucm-red text-white font-extrabold text-xl py-3 rounded-xl shadow-lg hover:opacity-90 transition-opacity">Apply Filters</button>
    </aside>

    <section>
      <div class="flex justify-between items-center mb-6 border-b pb-3">
        <h2 class="text-3xl font-bold text-gray-900">Opportunities <span class="text-xl font-normal text-gray-500">(54 Total)</span></h2>
      </div>
      <div class="space-y-6">
        <div class="bg-white p-6 rounded-2xl shadow-xl border border-gray-100 hover:shadow-2xl transition duration-200 cursor-pointer" onclick="openModal()">
          <h3 class="text-2xl font-bold text-gray-900">A. Ralph Boxell Eagle Scout Scholarship</h3>
          <p class="text-gray-600 mt-2 mb-4 text-lg">Available through the UCM Alumni Foundation for active Eagle Scouts enrolled at UCM.</p>
        </div>
      </div>
    </section>
  </div>
</main>

<!-- RESULTS VIEW -->
<main id="view-results" class="hidden flex-grow w-full p-10 overflow-y-auto">
  <div class="space-y-10">
    <div class="bg-white p-8 rounded-2xl shadow-xl border-t-8 border-ucm-gold">
      <h2 class="text-5xl font-extrabold text-gray-900 mb-4 flex items-center">
        <svg class="w-12 h-12 text-ucm-red mr-4" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path></svg>
        Your Scholarships Are Ready!
      </h2>
      <p class="text-2xl text-gray-600 mt-4">
        Congratulations! Review the status of the specific scholarships you applied for below.
      </p>
    </div>
  </div>
</main>

<footer class="bg-gray-800 text-white flex-shrink-0 py-4 px-10 text-center text-lg">
  <p class="text-gray-400">&copy; 2025 University of Central Missouri. Financial Aid & Scholarship Office.</p>
</footer>
</div>

<!-- MODAL -->
<div id="detail-modal" class="hidden fixed inset-0 bg-gray-900 bg-opacity-75 z-50 flex justify-center items-center p-4" onclick="closeModal()">
  <div class="bg-white w-full max-w-5xl max-h-[90vh] rounded-2xl shadow-2xl overflow-y-auto text-2xl" onclick="event.stopPropagation()">
    <div class="sticky top-0 bg-white p-8 border-b flex justify-between items-start z-10">
      <h2 class="text-4xl font-extrabold text-ucm-red">A. Ralph Boxell Eagle Scout Scholarship</h2>
      <button onclick="closeModal()" class="text-gray-400 hover:text-gray-800 transition-colors p-2 rounded-full">
        <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
      </button>
    </div>
    <div class="p-8 space-y-8">
      <p class="text-gray-700 leading-relaxed">
        This scholarship supports students demonstrating leadership and service. Preference is given to active Eagle Scouts.
      </p>
      <button class="w-full bg-ucm-red text-white font-extrabold py-4 rounded-xl shadow-lg hover:bg-ucm-red/90 transition-opacity text-2xl focus:outline-none focus:ring-4 focus:ring-ucm-red/50">
        Apply Now
      </button>
    </div>
  </div>
</div>

</body>
</html>
