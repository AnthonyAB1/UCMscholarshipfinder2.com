<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>UCM Scholarship Portal - Home/Search</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>
<script>
  // Tailwind custom config
  tailwind.config = {
    theme: {
      extend: {
        colors: {
          'ucm-red': '#990000',
          'ucm-gold': '#ffcc00',
          'ucm-light': '#fefefe',
          'ucm-surface': '#f9fafb'
        },
        fontFamily: {
          sans: ['Inter','sans-serif']
        }
      }
    }
  };

  // View switching
  function switchView(viewId) {
    const views = ['view-home','view-results'];
    views.forEach(id => {
      const el = document.getElementById(id);
      if (el) el.classList.add('hidden');
    });
    const newView = document.getElementById(viewId);
    if (!newView) return;
    newView.classList.remove('hidden');
    newView.scrollTop = 0;

    // nav highlight
    const isHome = viewId === 'view-home';
    const navHome = document.getElementById('nav-home');
    const navResults = document.getElementById('nav-results');
    if(navHome && navResults) {
      navHome.classList.toggle('bg-ucm-gold', isHome);
      navHome.classList.toggle('bg-white', !isHome);
      navHome.classList.toggle('text-ucm-red', isHome);
      navHome.classList.toggle('text-gray-700', !isHome);
      navResults.classList.toggle('bg-ucm-gold', !isHome);
      navResults.classList.toggle('bg-white', isHome);
      navResults.classList.toggle('text-ucm-red', !isHome);
      navResults.classList.toggle('text-gray-700', isHome);
    }
  }

  // Modal
  function openModal() {
    document.getElementById('detail-modal')?.classList.remove('hidden');
  }
  function closeModal() {
    document.getElementById('detail-modal')?.classList.add('hidden');
  }

  document.addEventListener('DOMContentLoaded', () => {
    switchView('view-home');
  });
</script>

<style>
  /* Page-level layout: center the app card and allow body scroll */
  body{
    font-family: 'Inter', sans-serif;
    background: #e5e7eb;
    margin: 0;
    padding: 20px 0;            /* vertical breathing room */
    display: flex;
    justify-content: center;   /* center the app */
    overflow-x: hidden;        /* avoid horizontal scroll */
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }

  /* App container: responsive and centered */
  #template-container{
    width: 95%;                /* roomy but shrinks on phones */
    max-width: 900px;         /* smaller max to appear compact */
    margin: 0 auto;
    background: #f9fafb;
    border-radius: 12px;
    box-shadow: 0 10px 40px rgba(0,0,0,0.15);
    display: flex;
    flex-direction: column;
    overflow: visible;        /* let content grow and body scroll */
  }

  /* sticky header behavior */
  header {
    position: sticky;
    top: 0;
    z-index: 40;
  }

  /* keep inner elements full-width and box-sizing stable */
  header, main, footer {
    width: 100%;
    box-sizing: border-box;
  }

  /* make the main area scrollable if the content is tall, but prefer body scroll */
  main {
    /* do not set fixed height here — let body control scrolling */
  }

  /* scrollbar (optional) */
  main::-webkit-scrollbar { width: 8px; }
  main::-webkit-scrollbar-track { background: #e5e7eb; }
  main::-webkit-scrollbar-thumb { background: #d1d5db; border-radius: 20px; border: 2px solid #e5e7eb; }

  /* small utility: reduce large spacing on phones */
  @media (max-width:640px){
    #template-container { width: 95%; }
    header { padding: 12px 16px; }
    main { padding: 12px; }
    footer { padding: 12px; }
  }
</style>
</head>
<body class="antialiased text-gray-800">

  <div id="template-container" class="bg-ucm-surface">

    <!-- HEADER -->
    <header class="bg-ucm-red text-white shadow px-6 py-4 sm:px-8 sm:py-6">
      <div class="flex items-center justify-between gap-4">
        <div class="flex items-center gap-4 cursor-pointer" onclick="switchView('view-home')">
          <div class="w-12 h-12 sm:w-14 sm:h-14 bg-white rounded-full flex items-center justify-center text-ucm-red font-extrabold text-lg sm:text-2xl">UCM</div>
          <div>
            <h1 class="text-lg sm:text-2xl font-bold">Scholarship Portal</h1>
          </div>
        </div>

        <nav class="flex items-center gap-2 sm:gap-4">
          <button id="nav-home" onclick="switchView('view-home')" class="bg-ucm-gold text-ucm-red font-semibold py-2 px-3 sm:py-2 sm:px-5 rounded-lg shadow border border-ucm-red text-sm sm:text-base">Scholarship Search</button>
          <button id="nav-results" onclick="switchView('view-results')" class="bg-white text-gray-700 font-semibold py-2 px-3 sm:py-2 sm:px-5 rounded-lg shadow border border-ucm-red text-sm sm:text-base">My Decisions</button>
          <button class="bg-ucm-gold text-ucm-red font-semibold py-2 px-3 rounded-lg hidden sm:inline-block">Sign In</button>
          <button class="p-2 text-white rounded-full hover:bg-white/20" title="User Info">
            <svg class="w-5 h-5 sm:w-6 sm:h-6" viewBox="0 0 24 24" fill="none" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
          </button>
        </nav>
      </div>
    </header>

    <!-- MAIN: Home view (default) -->
    <main id="view-home" class="p-6 sm:p-8 md:p-10">
      <div class="space-y-6 sm:space-y-8">

        <!-- Hero -->
        <section class="bg-white p-4 sm:p-6 rounded-xl shadow border-t-4 border-ucm-red">
          <h2 class="text-lg sm:text-2xl font-extrabold flex items-center gap-3">
            <svg class="w-6 h-6 text-ucm-gold" viewBox="0 0 20 20" fill="currentColor"><path d="M5 4a2 2 0 012-2h6a2 2 0 012 2v14l-5-2.5L5 18V4z"/></svg>
            Find Your Funding
          </h2>
          <p class="mt-2 text-sm sm:text-base text-gray-600">Welcome to the UCM Scholarship Portal! Use the tools below to explore scholarship opportunities, grants, and awards. Complete the General Application to be matched with dozens of awards automatically.</p>
          <a href="#" onclick="event.preventDefault()" class="inline-block mt-3 bg-ucm-gold text-ucm-red font-semibold py-2 px-4 rounded-lg text-sm sm:text-base shadow">Complete General Application →</a>
        </section>

        <!-- Filters -->
        <aside class="bg-white p-4 sm:p-6 rounded-xl shadow border">
          <h3 class="text-base sm:text-lg font-bold mb-3">Filter Opportunities</h3>
          <div class="space-y-3">
            <div>
              <label class="block text-sm text-gray-700 mb-1">Search by Keyword</label>
              <input id="keyword-search" type="text" placeholder="e.g., Biology" class="w-full p-2 sm:p-3 border rounded-lg text-sm sm:text-base focus:ring-ucm-red focus:border-ucm-red" />
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
              <div>
                <label class="block text-sm text-gray-700 mb-1">Department Scope</label>
                <select id="department-filter" class="w-full p-2 sm:p-3 border rounded-lg text-sm sm:text-base">
                  <option>All Departments (54)</option>
                  <option>Harmon College of Business</option>
                </select>
              </div>

              <div>
                <label class="block text-sm text-gray-700 mb-1">Award Type</label>
                <div class="grid grid-cols-2 gap-2">
                  <label class="flex items-center text-sm"><input type="checkbox" class="mr-2">Scholarship</label>
                  <label class="flex items-center text-sm"><input type="checkbox" class="mr-2">Grant</label>
                  <label class="flex items-center text-sm"><input type="checkbox" class="mr-2">Award</label>
                  <label class="flex items-center text-sm"><input type="checkbox" class="mr-2">Pending</label>
                </div>
              </div>
            </div>

            <button class="w-full bg-ucm-red text-white py-2 rounded-lg font-semibold mt-2">Apply Filters</button>
          </div>
        </aside>

        <!-- Opportunities list -->
        <section>
          <div class="flex flex-col sm:flex-row sm:justify-between sm:items-center gap-3 mb-4">
            <h3 class="text-base sm:text-xl font-bold">Opportunities <span class="text-sm text-gray-500">(54)</span></h3>
            <div class="flex items-center gap-2">
              <label class="text-sm text-gray-600">Sort</label>
              <select id="sort-by" class="p-1 sm:p-2 border rounded text-sm">
                <option>Deadline (Earliest)</option>
                <option>Award Amount (High to Low)</option>
              </select>
            </div>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <!-- Card 1 -->
            <article class="bg-white p-4 sm:p-5 rounded-xl shadow border cursor-pointer" onclick="openModal()">
              <div class="flex justify-between items-start gap-3">
                <h4 class="text-sm sm:text-lg font-bold hover:text-ucm-red">A. Ralph Boxell Eagle Scout Scholarship</h4>
                <button class="p-1 text-gray-500" title="Save"><svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor"><path d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z" stroke-width="1.5"/></svg></button>
              </div>
              <p class="text-xs sm:text-sm text-gray-600 mt-2">Available through the UCM Alumni Foundation for active Eagle Scouts enrolled at UCM.</p>
              <div class="flex flex-wrap gap-2 mt-3 text-xs sm:text-sm">
                <span class="bg-gray-100 px-2 py-1 rounded-full">Amount: Varies</span>
                <span class="bg-ucm-gold/20 text-ucm-red px-2 py-1 rounded-full">Deadline: Mar 15, 2026</span>
                <span class="bg-ucm-red/10 text-ucm-red px-2 py-1 rounded-full">General Application</span>
              </div>
            </article>

            <!-- Card 2 -->
            <article class="bg-white p-4 sm:p-5 rounded-xl shadow border">
              <div class="flex justify-between items-start gap-3">
                <h4 class="text-sm sm:text-lg font-bold hover:text-ucm-red">Harmon College Business Graduate Scholarship</h4>
                <button class="p-1 text-ucm-red" title="Saved"><svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z"/></svg></button>
              </div>
              <p class="text-xs sm:text-sm text-gray-600 mt-2">Established to support outstanding graduate students within the Harmon College.</p>
              <div class="flex flex-wrap gap-2 mt-3 text-xs sm:text-sm">
                <span class="bg-gray-100 px-2 py-1 rounded-full">Amount: Full Ride</span>
                <span class="bg-blue-100 text-blue-700 px-2 py-1 rounded-full">Requires Essay</span>
                <span class="bg-ucm-red/10 text-ucm-red px-2 py-1 rounded-full">Harmon Specific</span>
              </div>
            </article>

            <!-- Card 3 -->
            <article class="bg-white p-4 sm:p-5 rounded-xl shadow border">
              <div class="flex justify-between items-start gap-3">
                <h4 class="text-sm sm:text-lg font-bold hover:text-ucm-red">Accountancy Scholarship Fund</h4>
                <button class="p-1 text-gray-500" title="Save"><svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor"><path d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z" stroke-width="1.5"/></svg></button>
              </div>
              <p class="text-xs sm:text-sm text-gray-600 mt-2">The Department of Accountancy Scholarship is available through the UCM Alumni Foundation.</p>
              <div class="flex flex-wrap gap-2 mt-3 text-xs sm:text-sm">
                <span class="bg-gray-100 px-2 py-1 rounded-full">Amount: $1,000</span>
                <span class="bg-ucm-gold/20 text-ucm-red px-2 py-1 rounded-full">Deadline: Mar 15, 2026</span>
                <span class="bg-ucm-red/10 text-ucm-red px-2 py-1 rounded-full">Departmental</span>
              </div>
            </article>
          </div>

          <!-- Pagination -->
          <div class="mt-6 flex justify-center">
            <nav class="flex gap-2">
              <button class="px-3 py-2 rounded-lg border">Previous</button>
              <button class="px-3 py-2 rounded-lg bg-ucm-red text-white">1</button>
              <button class="px-3 py-2 rounded-lg border">2</button>
              <button class="px-3 py-2 rounded-lg border">3</button>
              <button class="px-3 py-2 rounded-lg border">Next</button>
            </nav>
          </div>
        </section>

      </div>
    </main>

    <!-- RESULTS view -->
    <main id="view-results" class="hidden p-6 sm:p-8 md:p-10">
      <div class="space-y-6">
        <section class="bg-white p-4 sm:p-6 rounded-xl shadow border-t-4 border-ucm-gold">
          <h2 class="text-lg sm:text-2xl font-extrabold">Your Decisions Are Ready!</h2>
          <p class="text-sm sm:text-base text-gray-600 mt-2">Review the status of scholarships you applied for below.</p>
        </section>

        <section class="space-y-4">
          <article class="bg-white p-4 sm:p-6 rounded-xl shadow border-l-4 border-green-600">
            <div class="flex justify-between items-start">
              <h3 class="font-bold text-green-700">UCM Presidential Leadership Scholarship</h3>
              <span class="font-extrabold text-green-600">$5,000</span>
            </div>
            <p class="text-sm sm:text-base text-gray-700 mt-2">Congratulations! You were selected — check your UCM email for next steps.</p>
          </article>
          <article class="bg-white p-4 sm:p-6 rounded-xl shadow border-l-4 border-gray-400">
            <div class="flex justify-between items-start">
              <h3 class="font-bold text-gray-700">Department of Computer Science Dean's Award</h3>
              <span class="font-extrabold text-gray-500">$30,000</span>
            </div>
            <p class="text-sm sm:text-base text-gray-700 mt-2">Decision finalized: not awarded.</p>
          </article>
        </section>
      </div>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white text-center py-4 rounded-b-xl">
      <p class="text-sm text-gray-400">&copy; 2025 University of Central Missouri. Financial Aid & Scholarship Office.</p>
    </footer>

  </div>

  <!-- DETAILS MODAL -->
  <div id="detail-modal" class="hidden fixed inset-0 z-50 bg-gray-900 bg-opacity-60 flex items-center justify-center p-4" onclick="closeModal()">
    <div class="bg-white w-full max-w-3xl rounded-xl shadow overflow-auto" onclick="event.stopPropagation()">
      <div class="sticky top-0 bg-white p-4 border-b flex justify-between items-center">
        <h3 class="font-extrabold text-ucm-red">A. Ralph Boxell Eagle Scout Scholarship</h3>
        <button class="p-2" onclick="closeModal()"><svg class="w-6 h-6" viewBox="0 0 24 24" fill="none" stroke="currentColor"><path d="M6 18L18 6M6 6l12 12" stroke-width="2"/></svg></button>
      </div>
      <div class="p-4 space-y-4">
        <div class="grid grid-cols-1 sm:grid-cols-3 gap-4">
          <div><span class="text-xs uppercase text-gray-500">Amount</span><div class="font-bold text-lg">Varies</div></div>
          <div><span class="text-xs uppercase text-gray-500">Deadline</span><div class="font-bold text-lg text-ucm-red">Mar 15, 2026</div></div>
          <div><span class="text-xs uppercase text-gray-500">Department</span><div class="font-bold text-lg">Alumni Foundation</div></div>
        </div>
        <div>
          <h4 class="font-bold">Description</h4>
          <p class="text-sm text-gray-700">This scholarship was established through ...</p>
        </div>
        <div>
          <h4 class="font-bold">Eligibility</h4>
          <ul class="list-disc ml-5 text-sm text-gray-700"><li>Active student</li><li>GPA 3.5+</li></ul>
        </div>
        <div>
          <button class="w-full bg-ucm-red text-white py-2 rounded-lg font-semibold">Apply Now</button>
        </div>
      </div>
    </div>
  </div>

</body>
</html>
