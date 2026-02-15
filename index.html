<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate">
    <title>LifeOS - ניהול פרויקטים</title>
    
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Rubik:wght@300;400;500;700;900&display=swap" rel="stylesheet">

    <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-auth.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-firestore.js"></script>

    <style>
        body { font-family: 'Rubik', sans-serif; background-color: #0f172a; color: white; }
        .glass { background: rgba(30, 41, 59, 0.7); backdrop-filter: blur(12px); border: 1px solid rgba(255, 255, 255, 0.1); }
        .dashboard-card { background: linear-gradient(145deg, #1e293b, #0f172a); border-radius: 28px; border: 1px solid rgba(255,255,255,0.05); }
    </style>
</head>
<body class="h-screen flex flex-col overflow-hidden text-right">

    <div id="authScreen" class="fixed inset-0 z-[100] flex flex-col items-center justify-center bg-slate-900 p-6">
        <div class="w-full max-w-sm glass p-8 rounded-[40px] text-center">
            <h1 class="text-3xl font-black mb-2">Life<span class="text-purple-400">OS</span></h1>
            <p class="text-slate-400 text-sm mb-8">מרחב עבודה אישי ומשותף</p>
            <input type="email" id="emailInput" placeholder="אימייל" class="w-full px-5 py-4 bg-slate-800 rounded-2xl mb-3 outline-none border border-slate-700 focus:border-purple-500 text-left" dir="ltr">
            <input type="password" id="passInput" placeholder="סיסמה" class="w-full px-5 py-4 bg-slate-800 rounded-2xl mb-6 outline-none border border-slate-700 focus:border-purple-500 text-left" dir="ltr">
            <button onclick="handleLogin()" class="w-full py-4 bg-purple-600 text-white font-bold rounded-2xl shadow-lg active:scale-95 transition mb-4">התחברות</button>
            <button onclick="handleSignup()" class="w-full py-3 bg-white/5 text-white font-bold rounded-2xl border border-white/10">יצירת חשבון חדש</button>
            <p class="text-[10px] text-slate-500 mt-4 italic">לאחר הרשמה, יש לאשר את המייל כדי להיכנס</p>
        </div>
    </div>

    <div id="appScreen" class="hidden flex-col h-full w-full">
        <header class="glass p-4 flex justify-between items-center sticky top-0 z-20">
            <div class="flex items-center gap-3">
                <button onclick="openHelpModal()" class="w-8 h-8 rounded-lg bg-white/5 text-slate-400 flex items-center justify-center"><i class="fas fa-question text-xs"></i></button>
                <h1 class="text-xl font-black">LifeOS</h1>
            </div>
            <div class="flex gap-2">
                <button onclick="toggleView()" id="viewBtn" class="px-4 py-2 bg-purple-600/20 text-purple-400 rounded-xl text-xs font-bold border border-purple-500/30">דשבורד</button>
                <button onclick="auth.signOut()" class="w-10 h-10 rounded-xl bg-white/5 text-slate-500 flex items-center justify-center"><i class="fas fa-sign-out-alt"></i></button>
            </div>
        </header>

        <main class="flex-1 overflow-y-auto p-6 bg-[#0f172a]">
            <div id="projectsView" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 pb-24"></div>
            
            <div id="dashboardView" class="hidden space-y-6">
                <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                    <div class="dashboard-card p-6 border-r-4 border-indigo-500">
                        <span class="text-[10px] text-slate-500 font-black uppercase tracking-widest">תקציב מתוכנן</span>
                        <div class="text-2xl font-black mt-2" id="statPlanned">₪0</div>
                    </div>
                    <div class="dashboard-card p-6 border-r-4 border-rose-500">
                        <span class="text-[10px] text-slate-500 font-black uppercase tracking-widest">הוצאה בפועל</span>
                        <div class="text-2xl font-black text-rose-400 mt-2" id="statSpent">₪0</div>
                    </div>
                </div>
                <div class="dashboard-card p-6 h-72">
                    <h3 class="text-xs font-bold text-slate-500 mb-4 uppercase">ניצול תקציב לפי פרויקט</h3>
                    <canvas id="budgetChart"></canvas>
                </div>
            </div>
        </main>
        
        <button onclick="alert('כאן תוסיף פרויקט חדש!')" class="fixed bottom-8 left-8 w-16 h-16 bg-purple-600 text-white rounded-2xl flex items-center justify-center shadow-2xl z-40 shadow-purple-500/20"><i class="fas fa-plus"></i></button>
    </div>

    <div id="helpModal" class="fixed inset-0 z-[110] hidden items-center justify-center bg-black/90 backdrop-blur-md p-4">
        <div class="bg-[#1e293b] w-full max-w-md rounded-[32px] p-8 border border-white/10">
            <h3 class="text-2xl font-black mb-6">ברוכים הבאים ל-LifeOS!</h3>
            <div class="space-y-4 text-sm text-slate-400">
                <p>1. <b>לוח אישי:</b> כל משתמש רואה רק את הפרויקטים שלו.</p>
                <p>2. <b>אישור מייל:</b> חובה לאשר את המייל שנשלח אליכם כדי להיכנס.</p>
                <p>3. <b>דשבורד:</b> עברו למסך דשבורד כדי לראות סיכום כספי של כל הפרויקטים.</p>
            </div>
            <button onclick="closeHelpModal()" class="w-full py-4 bg-indigo-600 text-white font-bold rounded-2xl mt-8">יאללה, התחלנו!</button>
        </div>
    </div>

    <script>
        const firebaseConfig = { 
            apiKey: "AIzaSyB7U5xw_FMThsmM2hNMRnkdMYnD2cutH2s", authDomain: "project-manager-4702c.firebaseapp.com", 
            projectId: "project-manager-4702c", storageBucket: "project-manager-4702c.firebasestorage.app", 
            messagingSenderId: "941533299304", appId: "1:941533299304:web:92f8940e93a96b1f8b71dd" 
        };
        firebase.initializeApp(firebaseConfig);
        const auth = firebase.auth(), db = firebase.firestore();

        let projects = [], isDashboard = false, budgetChart = null;

        // בדיקת סטטוס משתמש - הפרדה מוחלטת
        auth.onAuthStateChanged(user => {
            if (user && user.emailVerified) {
                document.getElementById('authScreen').classList.add('hidden');
                document.getElementById('appScreen').classList.remove('hidden');
                loadUserData(user.email.toLowerCase());
            } else {
                document.getElementById('authScreen').classList.remove('hidden');
                document.getElementById('appScreen').classList.add('hidden');
            }
        });

        function handleLogin() {
            const email = document.getElementById('emailInput').value.trim();
            const pass = document.getElementById('passInput').value;
            auth.signInWithEmailAndPassword(email, pass).catch(err => alert("שגיאה: " + err.message));
        }

        function handleSignup() {
            const email = document.getElementById('emailInput').value.trim();
            const pass = document.getElementById('passInput').value;
            auth.createUserWithEmailAndPassword(email, pass).then(cred => {
                cred.user.sendEmailVerification();
                alert("נרשמת בהצלחה! שלחנו לך מייל אישור. אנא אשר אותו והתחבר.");
            }).catch(err => alert("שגיאה ברישום: " + err.message));
        }

        function loadUserData(email) {
            db.collection('life_projects').where('collaborators', 'array-contains', email)
              .onSnapshot(snap => {
                  projects = snap.docs.map(doc => ({id: doc.id, ...doc.data()}));
                  renderProjects();
                  if(isDashboard) updateDashboard();
              });
        }

        function toggleView() {
            isDashboard = !isDashboard;
            document.getElementById('projectsView').classList.toggle('hidden', isDashboard);
            document.getElementById('dashboardView').classList.toggle('hidden', !isDashboard);
            document.getElementById('viewBtn').innerText = isDashboard ? "פרויקטים" : "דשבורד";
            if(isDashboard) updateDashboard();
        }

        function updateDashboard() {
            let planned = 0, spent = 0;
            projects.forEach(p => {
                planned += Number(p.budget || 0);
                spent += p.tasks ? p.tasks.reduce((s,t) => s + (Number(t.cost)||0), 0) : 0;
            });
            document.getElementById('statPlanned').innerText = `₪${planned.toLocaleString()}`;
            document.getElementById('statSpent').innerText = `₪${spent.toLocaleString()}`;
            renderChart();
        }

        function renderChart() {
            const ctx = document.getElementById('budgetChart').getContext('2d');
            if(budgetChart) budgetChart.destroy();
            budgetChart = new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: projects.map(p => p.title),
                    datasets: [{ label: 'הוצאה בפועל', data: projects.map(p => p.tasks ? p.tasks.reduce((s,t)=>s+(Number(t.cost)||0),0) : 0), backgroundColor: '#10b981', borderRadius: 10 }]
                },
                options: { responsive: true, maintainAspectRatio: false, scales: { y: { ticks: { color: '#64748b' } }, x: { ticks: { color: '#64748b' } } } }
            });
        }

        function renderProjects() {
            const grid = document.getElementById('projectsView');
            if(projects.length === 0) {
                grid.innerHTML = '<div class="col-span-full text-center py-20 text-slate-500">אין פרויקטים להצגה. לחצו על ה-(+) ליצירת פרויקט ראשון!</div>';
                return;
            }
            grid.innerHTML = projects.map(p => `
                <div class="dashboard-card p-6">
                    <h3 class="text-xl font-bold mb-2">${p.title}</h3>
                    <div class="text-[10px] text-slate-500 uppercase font-black">${p.category || 'כללי'}</div>
                </div>
            `).join('');
        }

        function openHelpModal() { document.getElementById('helpModal').classList.replace('hidden', 'flex'); }
        function closeHelpModal() { document.getElementById('helpModal').classList.replace('flex', 'hidden'); }
    </script>
</body>
</html>
