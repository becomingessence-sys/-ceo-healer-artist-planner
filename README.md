# -ceo-healer-artist-planner
My Lifebook 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CEO-Healer-Artist Life Planner</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'deep-purple': '#4C1D95',
                        'soul-purple': '#6B46C1',
                        'gold': '#F59E0B',
                        'teal': '#0D9488',
                        'light-teal': '#5EEAD4'
                    }
                }
            }
        }
    </script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:wght@400;500;600;700&display=swap');
        
        body {
            font-family: 'Inter', sans-serif;
        }
        
        .heading-font {
            font-family: 'Playfair Display', serif;
        }
        
        .vision-card {
            background: linear-gradient(135deg, #4C1D95 0%, #6B46C1 50%, #0D9488 100%);
            position: relative;
            overflow: hidden;
        }
        
        .vision-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><circle cx="20" cy="20" r="2" fill="rgba(245,158,11,0.3)"/><circle cx="80" cy="40" r="1.5" fill="rgba(245,158,11,0.4)"/><circle cx="40" cy="80" r="1" fill="rgba(245,158,11,0.2)"/></svg>');
        }
        
        .goal-card {
            background: linear-gradient(135deg, #F8FAFC 0%, #F1F5F9 100%);
            border-left: 4px solid;
            transition: all 0.3s ease;
        }
        
        .goal-card:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }
        
        .habit-circle {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            border: 3px solid #E5E7EB;
            cursor: pointer;
            transition: all 0.2s ease;
            position: relative;
        }
        
        .habit-circle.completed {
            background: linear-gradient(135deg, #0D9488, #14B8A6);
            border-color: #0D9488;
        }
        
        .habit-circle.completed::after {
            content: '✓';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            color: white;
            font-weight: bold;
        }
        
        .time-block {
            background: linear-gradient(135deg, #FEF3C7 0%, #FDE68A 100%);
            border-left: 4px solid #F59E0B;
        }
        
        .nav-tab {
            transition: all 0.3s ease;
            border-bottom: 3px solid transparent;
        }
        
        .nav-tab.active {
            border-bottom-color: #F59E0B;
            color: #4C1D95;
        }
        
        .section {
            display: none;
        }
        
        .section.active {
            display: block;
            animation: fadeIn 0.5s ease-in;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .energy-dot {
            transition: all 0.2s ease;
        }
        
        .energy-dot:hover {
            transform: scale(1.2);
        }
    </style>
</head>
<body class="bg-gradient-to-br from-purple-50 via-white to-teal-50 min-h-screen">
    <!-- Header -->
    <header class="bg-white/90 backdrop-blur-sm border-b border-gray-200 sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-6 py-4">
            <div class="flex items-center justify-between">
                <div class="flex items-center space-x-4">
                    <div class="w-12 h-12 bg-gradient-to-r from-deep-purple to-teal rounded-full flex items-center justify-center">
                        <span class="text-white font-bold text-xl">✨</span>
                    </div>
                    <div>
                        <h1 class="text-2xl font-bold heading-font text-deep-purple">CEO • Healer • Artist</h1>
                        <p class="text-sm text-gray-600">Life Planner & Vision Tracker</p>
                    </div>
                </div>
                <div class="flex items-center space-x-6">
                    <div class="text-center">
                        <div class="text-lg font-bold text-gold">£1,847</div>
                        <div class="text-xs text-gray-600">This Month</div>
                    </div>
                    <div class="text-center">
                        <div class="text-lg font-bold text-teal">23</div>
                        <div class="text-xs text-gray-600">Day Streak</div>
                    </div>
                </div>
            </div>
        </div>
    </header>

    <!-- Navigation -->
    <nav class="bg-white border-b border-gray-100">
        <div class="max-w-7xl mx-auto px-6">
            <div class="flex space-x-8">
                <button onclick="showSection('vision')" class="nav-tab active py-4 px-2 text-sm font-medium">Vision Board</button>
                <button onclick="showSection('goals')" class="nav-tab py-4 px-2 text-sm font-medium">Goals & Milestones</button>
                <button onclick="showSection('weekly')" class="nav-tab py-4 px-2 text-sm font-medium">Weekly Flow</button>
                <button onclick="showSection('daily')" class="nav-tab py-4 px-2 text-sm font-medium">Daily Focus</button>
                <button onclick="showSection('habits')" class="nav-tab py-4 px-2 text-sm font-medium">Habits & Rhythms</button>
                <button onclick="showSection('reflection')" class="nav-tab py-4 px-2 text-sm font-medium">Dream Reflections</button>
            </div>
        </div>
    </nav>

    <main class="max-w-7xl mx-auto px-6 py-8">
        <!-- Vision Board Section -->
        <div id="vision" class="section active">
            <div class="vision-card rounded-3xl p-8 mb-8 text-white relative z-10">
                <h2 class="text-3xl font-bold heading-font mb-6">Your Vision & Dreams</h2>
                <div class="grid md:grid-cols-3 gap-6">
                    <div class="bg-white/10 backdrop-blur-sm rounded-2xl p-6">
                        <h3 class="font-semibold mb-3 flex items-center">
                            <span class="mr-2">👑</span> CEO Vision
                        </h3>
                        <textarea class="w-full bg-white/20 border-0 rounded-lg p-3 text-white placeholder-white/70 resize-none" rows="4" placeholder="Building Becoming Essence into a transformational empire...">Building Becoming Essence into a transformational empire that serves thousands...</textarea>
                    </div>
                    <div class="bg-white/10 backdrop-blur-sm rounded-2xl p-6">
                        <h3 class="font-semibold mb-3 flex items-center">
                            <span class="mr-2">🌿</span> Healer Vision
                        </h3>
                        <textarea class="w-full bg-white/20 border-0 rounded-lg p-3 text-white placeholder-white/70 resize-none" rows="4" placeholder="Creating sacred spaces for healing...">Creating sacred spaces for healing, growth, and authentic connection...</textarea>
                    </div>
                    <div class="bg-white/10 backdrop-blur-sm rounded-2xl p-6">
                        <h3 class="font-semibold mb-3 flex items-center">
                            <span class="mr-2">🎨</span> Artist Vision
                        </h3>
                        <textarea class="w-full bg-white/20 border-0 rounded-lg p-3 text-white placeholder-white/70 resize-none" rows="4" placeholder="Expressing my soul through music...">Expressing my soul through music, movement, and creative collaboration...</textarea>
                    </div>
                </div>
            </div>

            <!-- Dream Symbols -->
            <div class="bg-white rounded-2xl shadow-sm border border-gray-100 p-6">
                <h3 class="text-xl font-semibold heading-font text-deep-purple mb-4">Dream Symbols & Meanings</h3>
                <div class="grid md:grid-cols-2 lg:grid-cols-6 gap-4">
                    <div class="text-center p-4 bg-gradient-to-b from-purple-50 to-purple-100 rounded-xl">
                        <div class="text-2xl mb-2">🛡️</div>
                        <div class="font-medium text-sm">Safety</div>
                        <div class="text-xs text-gray-600 mt-1">Grounding & Security</div>
                    </div>
                    <div class="text-center p-4 bg-gradient-to-b from-gold/20 to-gold/30 rounded-xl">
                        <div class="text-2xl mb-2">⏰</div>
                        <div class="font-medium text-sm">Timing</div>
                        <div class="text-xs text-gray-600 mt-1">Divine Alignment</div>
                    </div>
                    <div class="text-center p-4 bg-gradient-to-b from-teal/20 to-teal/30 rounded-xl">
                        <div class="text-2xl mb-2">💝</div>
                        <div class="font-medium text-sm">Intimacy</div>
                        <div class="text-xs text-gray-600 mt-1">Deep Connection</div>
                    </div>
                    <div class="text-center p-4 bg-gradient-to-b from-green-50 to-green-100 rounded-xl">
                        <div class="text-2xl mb-2">🔄</div>
                        <div class="font-medium text-sm">Reciprocity</div>
                        <div class="text-xs text-gray-600 mt-1">Balanced Exchange</div>
                    </div>
                    <div class="text-center p-4 bg-gradient-to-b from-blue-50 to-blue-100 rounded-xl">
                        <div class="text-2xl mb-2">🔮</div>
                        <div class="font-medium text-sm">Clarity</div>
                        <div class="text-xs text-gray-600 mt-1">Clear Vision</div>
                    </div>
                    <div class="text-center p-4 bg-gradient-to-b from-red-50 to-red-100 rounded-xl">
                        <div class="text-2xl mb-2">⚔️</div>
                        <div class="font-medium text-sm">Discipline</div>
                        <div class="text-xs text-gray-600 mt-1">Inner Strength</div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Goals & Milestones Section -->
        <div id="goals" class="section">
            <h2 class="text-2xl font-bold heading-font text-deep-purple mb-6">Goals & Milestones</h2>
            
            <!-- Financial Progress -->
            <div class="bg-white rounded-2xl shadow-sm border border-gray-100 p-6 mb-6">
                <h3 class="font-semibold text-deep-purple mb-4 flex items-center">
                    <span class="mr-2">💰</span> Financial Journey
                </h3>
                
                <div class="grid md:grid-cols-3 gap-4 mb-6">
                    <div class="p-4 bg-gradient-to-br from-purple-50 to-purple-100 rounded-xl border-l-4 border-deep-purple">
                        <h4 class="font-medium text-sm text-deep-purple mb-2">TC (Tania Camara)</h4>
                        <div class="text-lg font-bold text-deep-purple">£687</div>
                        <div class="text-xs text-gray-600 mt-1">Coaching, speaking, personal work</div>
                    </div>
                    
                    <div class="p-4 bg-gradient-to-br from-teal-50 to-teal-100 rounded-xl border-l-4 border-teal">
                        <h4 class="font-medium text-sm text-teal mb-2">BE (Becoming Essence)</h4>
                        <div class="text-lg font-bold text-teal">£823</div>
                        <div class="text-xs text-gray-600 mt-1">Journals, courses, healing work</div>
                    </div>
                    
                    <div class="p-4 bg-gradient-to-br from-gold/20 to-gold/30 rounded-xl border-l-4 border-gold">
                        <h4 class="font-medium text-sm text-gold mb-2">VDS (Vibra Dance)</h4>
                        <div class="text-lg font-bold text-gold">£337</div>
                        <div class="text-xs text-gray-600 mt-1">Classes, workshops, training</div>
                    </div>
                </div>
                
                <div class="grid md:grid-cols-4 gap-4 mb-4">
                    <div class="p-4 bg-gradient-to-br from-green-50 to-green-100 rounded-xl text-center">
                        <div class="text-xs text-gray-600 mb-1">Total Income</div>
                        <div class="text-xl font-bold text-green-600">£1,847</div>
                    </div>
                    
                    <div class="p-4 bg-gradient-to-br from-red-50 to-red-100 rounded-xl text-center">
                        <div class="text-xs text-gray-600 mb-1">Business Expenses</div>
                        <div class="text-xl font-bold text-red-600">£423</div>
                    </div>
                    
                    <div class="p-4 bg-gradient-to-br from-blue-50 to-blue-100 rounded-xl text-center">
                        <div class="text-xs text-gray-600 mb-1">Net Income</div>
                        <div class="text-xl font-bold text-blue-600">£1,424</div>
                    </div>
                    
                    <div class="p-4 bg-gradient-to-br from-gold/20 to-gold/30 rounded-xl text-center">
                        <div class="text-xs text-gray-600 mb-1">Monthly Target</div>
                        <div class="text-xl font-bold text-gold">£2,500</div>
                    </div>
                </div>
                
                <div>
                    <div class="flex justify-between text-sm mb-2">
                        <span>Progress to Target</span>
                        <span>57% (£1,424 / £2,500)</span>
                    </div>
                    <div class="w-full bg-gray-200 rounded-full h-3">
                        <div class="bg-gradient-to-r from-gold to-teal h-3 rounded-full transition-all duration-500" style="width: 57%"></div>
                    </div>
                </div>
            </div>
            
            <!-- Quarterly Goals -->
            <div class="grid md:grid-cols-2 gap-6">
                <div class="goal-card rounded-2xl p-6 border-l-deep-purple">
                    <h3 class="font-semibold text-deep-purple mb-4 heading-font">Q1 2024 Goals</h3>
                    <div class="space-y-3">
                        <div class="flex items-center space-x-3">
                            <input type="checkbox" class="w-4 h-4 text-teal rounded" checked>
                            <span class="text-sm line-through text-gray-500">Launch Becoming Essence website</span>
                        </div>
                        <div class="flex items-center space-x-3">
                            <input type="checkbox" class="w-4 h-4 text-teal rounded" checked>
                            <span class="text-sm line-through text-gray-500">Record first 5 podcast episodes</span>
                        </div>
                        <div class="flex items-center space-x-3">
                            <input type="checkbox" class="w-4 h-4 text-teal rounded">
                            <span class="text-sm">Reach £2,500 monthly income</span>
                        </div>
                        <div class="flex items-center space-x-3">
                            <input type="checkbox" class="w-4 h-4 text-teal rounded">
                            <span class="text-sm">Master 10-second handstand hold</span>
                        </div>
                    </div>
                </div>
                
                <div class="goal-card rounded-2xl p-6 border-l-gold">
                    <h3 class="font-semibold text-deep-purple mb-4 heading-font">Creative Projects</h3>
                    <div class="space-y-3">
                        <div class="flex items-center space-x-3">
                            <input type="checkbox" class="w-4 h-4 text-gold rounded">
                            <span class="text-sm">Complete kora composition series</span>
                        </div>
                        <div class="flex items-center space-x-3">
                            <input type="checkbox" class="w-4 h-4 text-gold rounded">
                            <span class="text-sm">Collaborate on Batuku dance video</span>
                        </div>
                        <div class="flex items-center space-x-3">
                            <input type="checkbox" class="w-4 h-4 text-gold rounded" checked>
                            <span class="text-sm line-through text-gray-500">Design healing journal templates</span>
                        </div>
                        <div class="flex items-center space-x-3">
                            <input type="checkbox" class="w-4 h-4 text-gold rounded">
                            <span class="text-sm">Host creative collaboration workshop</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Weekly Flow Section -->
        <div id="weekly" class="section">
            <div class="bg-white rounded-2xl shadow-sm border border-gray-100 p-6">
                <h2 class="text-2xl font-bold heading-font text-deep-purple mb-6">Weekly Flow</h2>
                <div class="text-sm text-gray-600 mb-6">Week of March 11-17, 2024</div>
                
                <div class="grid lg:grid-cols-7 gap-4">
                    <div class="space-y-3">
                        <h3 class="font-semibold text-center text-deep-purple">Monday</h3>
                        <div class="space-y-2">
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">6:00 AM</div>
                                <div>Morning ritual & journaling</div>
                            </div>
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">9:00 AM</div>
                                <div>Content creation</div>
                            </div>
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">7:00 PM</div>
                                <div>Capoeira training</div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="space-y-3">
                        <h3 class="font-semibold text-center text-deep-purple">Tuesday</h3>
                        <div class="space-y-2">
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">7:00 AM</div>
                                <div>Strength training</div>
                            </div>
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">10:00 AM</div>
                                <div>Podcast recording</div>
                            </div>
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">8:00 PM</div>
                                <div>Kora practice</div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="space-y-3">
                        <h3 class="font-semibold text-center text-deep-purple">Wednesday</h3>
                        <div class="space-y-2">
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">6:30 AM</div>
                                <div>Yoga & mobility</div>
                            </div>
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">9:00 AM</div>
                                <div>Business development</div>
                            </div>
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">7:30 PM</div>
                                <div>Dance practice</div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="space-y-3">
                        <h3 class="font-semibold text-center text-deep-purple">Thursday</h3>
                        <div class="space-y-2">
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">7:00 AM</div>
                                <div>Handstand practice</div>
                            </div>
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">10:00 AM</div>
                                <div>Client sessions</div>
                            </div>
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">8:00 PM</div>
                                <div>Piano composition</div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="space-y-3">
                        <h3 class="font-semibold text-center text-deep-purple">Friday</h3>
                        <div class="space-y-2">
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">6:00 AM</div>
                                <div>Capoeira training</div>
                            </div>
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">9:00 AM</div>
                                <div>Content batch creation</div>
                            </div>
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">7:00 PM</div>
                                <div>Social connections</div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="space-y-3">
                        <h3 class="font-semibold text-center text-deep-purple">Saturday</h3>
                        <div class="space-y-2">
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">8:00 AM</div>
                                <div>Nature & reflection</div>
                            </div>
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">2:00 PM</div>
                                <div>Creative collaboration</div>
                            </div>
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">8:00 PM</div>
                                <div>Family time</div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="space-y-3">
                        <h3 class="font-semibold text-center text-deep-purple">Sunday</h3>
                        <div class="space-y-2">
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">9:00 AM</div>
                                <div>Spiritual practice</div>
                            </div>
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">11:00 AM</div>
                                <div>Weekly planning</div>
                            </div>
                            <div class="time-block rounded-lg p-3 text-sm">
                                <div class="font-medium">6:00 PM</div>
                                <div>Rest & restoration</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Daily Focus Section -->
        <div id="daily" class="section">
            <!-- Top 3 Priorities -->
            <div class="bg-white rounded-2xl shadow-sm border border-gray-100 p-6 mb-6">
                <h2 class="text-2xl font-bold heading-font text-deep-purple mb-6 flex items-center">
                    <span class="mr-3">🎯</span> Top 3 Priorities
                </h2>
                <div class="space-y-4">
                    <div class="flex items-center space-x-4 p-4 bg-gradient-to-r from-deep-purple/10 to-teal/10 rounded-xl border-l-4 border-deep-purple">
                        <input type="checkbox" class="w-6 h-6 text-deep-purple rounded">
                        <input type="text" class="flex-1 bg-transparent border-0 focus:outline-none font-semibold text-lg" placeholder="Record podcast episode on 'Healing Through Movement'" value="Record podcast episode on 'Healing Through Movement'">
                    </div>
                    <div class="flex items-center space-x-4 p-4 bg-gradient-to-r from-gold/10 to-teal/10 rounded-xl border-l-4 border-gold">
                        <input type="checkbox" class="w-6 h-6 text-gold rounded">
                        <input type="text" class="flex-1 bg-transparent border-0 focus:outline-none font-semibold text-lg" placeholder="Complete journal template designs" value="Complete journal template designs">
                    </div>
                    <div class="flex items-center space-x-4 p-4 bg-gradient-to-r from-teal/10 to-deep-purple/10 rounded-xl border-l-4 border-teal">
                        <input type="checkbox" class="w-6 h-6 text-teal rounded">
                        <input type="text" class="flex-1 bg-transparent border-0 focus:outline-none font-semibold text-lg" placeholder="Practice kora composition for 45 minutes" value="Practice kora composition for 45 minutes">
                    </div>
                </div>
            </div>

            <!-- Energy Level Indicator -->
            <div class="bg-white rounded-2xl shadow-sm border border-gray-100 p-6 mb-6">
                <div class="flex items-center justify-between mb-4">
                    <h2 class="text-xl font-bold heading-font text-deep-purple">🔋 Energy Capacity Check-In</h2>
                    <div class="flex items-center space-x-2">
                        <span class="text-sm text-gray-600">Current Energy:</span>
                        <div id="current-energy-display" class="px-3 py-1 rounded-full text-sm font-medium bg-green-100 text-green-800">High Energy</div>
                    </div>
                </div>
                
                <div class="grid md:grid-cols-4 gap-4 mb-4">
                    <div class="text-center">
                        <div class="text-sm text-gray-600 mb-2">Physical Energy</div>
                        <div class="flex justify-center space-x-1 mb-2">
                            <div class="energy-dot w-3 h-3 rounded-full bg-teal cursor-pointer" onclick="setEnergyLevel('physical', 1)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-teal cursor-pointer" onclick="setEnergyLevel('physical', 2)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-teal cursor-pointer" onclick="setEnergyLevel('physical', 3)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-gray-200 cursor-pointer" onclick="setEnergyLevel('physical', 4)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-gray-200 cursor-pointer" onclick="setEnergyLevel('physical', 5)"></div>
                        </div>
                        <div class="text-xs text-teal font-medium">Moderate</div>
                    </div>
                    
                    <div class="text-center">
                        <div class="text-sm text-gray-600 mb-2">Mental Clarity</div>
                        <div class="flex justify-center space-x-1 mb-2">
                            <div class="energy-dot w-3 h-3 rounded-full bg-gold cursor-pointer" onclick="setEnergyLevel('mental', 1)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-gold cursor-pointer" onclick="setEnergyLevel('mental', 2)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-gold cursor-pointer" onclick="setEnergyLevel('mental', 3)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-gold cursor-pointer" onclick="setEnergyLevel('mental', 4)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-gray-200 cursor-pointer" onclick="setEnergyLevel('mental', 5)"></div>
                        </div>
                        <div class="text-xs text-gold font-medium">High</div>
                    </div>
                    
                    <div class="text-center">
                        <div class="text-sm text-gray-600 mb-2">Creative Flow</div>
                        <div class="flex justify-center space-x-1 mb-2">
                            <div class="energy-dot w-3 h-3 rounded-full bg-deep-purple cursor-pointer" onclick="setEnergyLevel('creative', 1)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-deep-purple cursor-pointer" onclick="setEnergyLevel('creative', 2)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-deep-purple cursor-pointer" onclick="setEnergyLevel('creative', 3)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-deep-purple cursor-pointer" onclick="setEnergyLevel('creative', 4)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-deep-purple cursor-pointer" onclick="setEnergyLevel('creative', 5)"></div>
                        </div>
                        <div class="text-xs text-deep-purple font-medium">Peak</div>
                    </div>
                    
                    <div class="text-center">
                        <div class="text-sm text-gray-600 mb-2">Emotional Balance</div>
                        <div class="flex justify-center space-x-1 mb-2">
                            <div class="energy-dot w-3 h-3 rounded-full bg-green-500 cursor-pointer" onclick="setEnergyLevel('emotional', 1)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-green-500 cursor-pointer" onclick="setEnergyLevel('emotional', 2)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-green-500 cursor-pointer" onclick="setEnergyLevel('emotional', 3)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-green-500 cursor-pointer" onclick="setEnergyLevel('emotional', 4)"></div>
                            <div class="energy-dot w-3 h-3 rounded-full bg-gray-200 cursor-pointer" onclick="setEnergyLevel('emotional', 5)"></div>
                        </div>
                        <div class="text-xs text-green-600 font-medium">High</div>
                    </div>
                </div>
                
                <div class="p-4 bg-gradient-to-r from-teal/10 to-deep-purple/10 rounded-lg border-l-4 border-teal">
                    <div class="text-sm font-medium text-deep-purple mb-2">🎯 Recommended Focus for Your Current Energy:</div>
                    <div class="text-sm text-gray-700">
                        Perfect for high-impact creative work! Consider recording content, deep writing, or transformational client sessions.
                    </div>
                </div>
            </div>
            
            <div class="grid lg:grid-cols-3 gap-6">
                <!-- Energy-Based Task Organization -->
                <div class="lg:col-span-2 bg-white rounded-2xl shadow-sm border border-gray-100 p-6">
                    <h2 class="text-xl font-bold heading-font text-deep-purple mb-6">⚡ Energy-Aligned Tasks</h2>
                    
                    <div class="space-y-6">
                        <!-- High Energy Tasks -->
                        <div>
                            <h3 class="font-semibold text-green-600 flex items-center mb-4">
                                <span class="mr-2">🚀</span> High-Energy Tasks (Peak Focus + Drive)
                            </h3>
                            <div class="space-y-3">
                                <div class="flex items-center space-x-3 p-3 bg-gradient-to-r from-green-50 to-emerald-50 rounded-lg border-l-4 border-green-500">
                                    <input type="checkbox" class="w-4 h-4 text-green-500 rounded">
                                    <input type="text" class="flex-1 bg-transparent border-0 focus:outline-none font-medium" value="Record podcast episode on 'Healing Through Movement'">
                                    <span class="text-xs text-gray-500 bg-white px-2 py-1 rounded">🎥 Content</span>
                                </div>
                                <div class="flex items-center space-x-3 p-3 bg-gradient-to-r from-green-50 to-emerald-50 rounded-lg border-l-4 border-green-500">
                                    <input type="checkbox" class="w-4 h-4 text-green-500 rounded">
                                    <input type="text" class="flex-1 bg-transparent border-0 focus:outline-none font-medium" value="Write transformational sales copy">
                                    <span class="text-xs text-gray-500 bg-white px-2 py-1 rounded">✍️ Writing</span>
                                </div>
                                <div class="flex items-center space-x-3 p-3 bg-gradient-to-r from-green-50 to-emerald-50 rounded-lg border-l-4 border-green-500">
                                    <input type="checkbox" class="w-4 h-4 text-green-500 rounded">
                                    <input type="text" class="flex-1 bg-transparent border-0 focus:outline-none font-medium" value="Afro-House movement practice">
                                    <span class="text-xs text-gray-500 bg-white px-2 py-1 rounded">💃 Movement</span>
                                </div>
                            </div>
                        </div>
                        
                        <!-- Medium Energy Tasks -->
                        <div>
                            <h3 class="font-semibold text-gold flex items-center mb-4">
                                <span class="mr-2">🌊</span> Medium-Energy Tasks (Flow & Consistency)
                            </h3>
                            <div class="space-y-3">
                                <div class="flex items-center space-x-3 p-3 bg-gradient-to-r from-yellow-50 to-amber-50 rounded-lg border-l-4 border-gold">
                                    <input type="checkbox" class="w-4 h-4 text-gold rounded">
                                    <input type="text" class="flex-1 bg-transparent border-0 focus:outline-none font-medium" value="Design Canva graphics for social posts">
                                    <span class="text-xs text-gray-500 bg-white px-2 py-1 rounded">🎨 Design</span>
                                </div>
                                <div class="flex items-center space-x-3 p-3 bg-gradient-to-r from-yellow-50 to-amber-50 rounded-lg border-l-4 border-gold">
                                    <input type="checkbox" class="w-4 h-4 text-gold rounded">
                                    <input type="text" class="flex-1 bg-transparent border-0 focus:outline-none font-medium" value="Build funnel pages for new course">
                                    <span class="text-xs text-gray-500 bg-white px-2 py-1 rounded">🔧 Tech</span>
                                </div>
                                <div class="flex items-center space-x-3 p-3 bg-gradient-to-r from-yellow-50 to-amber-50 rounded-lg border-l-4 border-gold">
                                    <input type="checkbox" class="w-4 h-4 text-gold rounded">
                                    <input type="text" class="flex-1 bg-transparent border-0 focus:outline-none font-medium" value="Deep kora composition work">
                                    <span class="text-xs text-gray-500 bg-white px-2 py-1 rounded">🎵 Creative</span>
                                </div>
                            </div>
                        </div>
                        
                        <!-- Low Energy Tasks -->
                        <div>
                            <h3 class="font-semibold text-teal flex items-center mb-4">
                                <span class="mr-2">🌙</span> Low-Energy Tasks (Gentle + Restorative)
                            </h3>
                            <div class="space-y-3">
                                <div class="flex items-center space-x-3 p-3 bg-gradient-to-r from-teal-50 to-cyan-50 rounded-lg border-l-4 border-teal">
                                    <input type="checkbox" class="w-4 h-4 text-teal rounded">
                                    <input type="text" class="flex-1 bg-transparent border-0 focus:outline-none font-medium" value="Organize digital files and schedule posts">
                                    <span class="text-xs text-gray-500 bg-white px-2 py-1 rounded">📁 Admin</span>
                                </div>
                                <div class="flex items-center space-x-3 p-3 bg-gradient-to-r from-teal-50 to-cyan-50 rounded-lg border-l-4 border-teal">
                                    <input type="checkbox" class="w-4 h-4 text-teal rounded">
                                    <input type="text" class="flex-1 bg-transparent border-0 focus:outline-none font-medium" value="Respond to comments and messages">
                                    <span class="text-xs text-gray-500 bg-white px-2 py-1 rounded">💬 Social</span>
                                </div>
                                <div class="flex items-center space-x-3 p-3 bg-gradient-to-r from-teal-50 to-cyan-50 rounded-lg border-l-4 border-teal">
                                    <input type="checkbox" class="w-4 h-4 text-teal rounded">
                                    <input type="text" class="flex-1 bg-transparent border-0 focus:outline-none font-medium" value="Dream journaling and integration">
                                    <span class="text-xs text-gray-500 bg-white px-2 py-1 rounded">🌙 Reflection</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Energy Reflection & Progress -->
                <div class="space-y-6">
                    <div class="bg-white rounded-2xl shadow-sm border border-gray-100 p-6">
                        <h3 class="font-semibold text-deep-purple mb-4 flex items-center">
                            <span class="mr-2">🌅</span> Morning Energy Intention
                        </h3>
                        <textarea class="w-full p-3 border border-gray-200 rounded-lg resize-none focus:ring-2 focus:ring-teal focus:border-transparent" rows="3" placeholder="How do I want to show up today? What energy am I bringing to my work and relationships?"></textarea>
                    </div>

                    <div class="bg-white rounded-2xl shadow-sm border border-gray-100 p-6">
                        <h3 class="font-semibold text-deep-purple mb-4 flex items-center">
                            <span class="mr-2">🌙</span> Evening Energy Reflection
                        </h3>
                        <textarea class="w-full p-3 border border-gray-200 rounded-lg resize-none focus:ring-2 focus:ring-deep-purple focus:border-transparent" rows="3" placeholder="How did my energy serve me today? What patterns am I noticing? What would I adjust tomorrow?"></textarea>
                        
                        <div class="mt-4 grid grid-cols-3 gap-2 text-center">
                            <button class="p-2 text-xs bg-green-100 text-green-700 rounded hover:bg-green-200 transition-colors">
                                😊 Energized
                            </button>
                            <button class="p-2 text-xs bg-yellow-100 text-yellow-700 rounded hover:bg-yellow-200 transition-colors">
                                ⚖️ Balanced
                            </button>
                            <button class="p-2 text-xs bg-red-100 text-red-700 rounded hover:bg-red-200 transition-colors">
                                😴 Drained
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Habits & Rhythms Section -->
        <div id="habits" class="section">
            <div class="grid lg:grid-cols-2 gap-8">
                <!-- Habit Tracker -->
                <div class="bg-white rounded-2xl shadow-sm border border-gray-100 p-6">
                    <h2 class="text-xl font-bold heading-font text-deep-purple mb-6">Sacred Rhythms Tracker</h2>
                    
                    <div class="space-y-6">
                        <!-- Physical Practices -->
                        <div>
                            <h3 class="font-semibold text-gray-900 mb-4 flex items-center">
                                <span class="mr-2">💪</span> Physical Practices
                            </h3>
                            <div class="space-y-4">
                                <div class="border border-gray-100 rounded-lg p-4">
                                    <div class="flex items-center justify-between mb-3">
                                        <span class="text-sm font-medium">Capoeira Training</span>
                                        <div class="flex space-x-2">
                                            <div class="habit-circle completed" title="Monday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Tuesday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle completed" title="Wednesday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Thursday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle completed" title="Friday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Saturday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Sunday" onclick="toggleHabit(this)"></div>
                                        </div>
                                    </div>
                                </div>
                                <div class="border border-gray-100 rounded-lg p-4">
                                    <div class="flex items-center justify-between mb-3">
                                        <span class="text-sm font-medium">Strength Training</span>
                                        <div class="flex space-x-2">
                                            <div class="habit-circle completed" title="Monday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle completed" title="Tuesday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Wednesday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle completed" title="Thursday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Friday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Saturday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Sunday" onclick="toggleHabit(this)"></div>
                                        </div>
                                    </div>
                                </div>
                                <div class="border border-gray-100 rounded-lg p-4">
                                    <div class="flex items-center justify-between mb-3">
                                        <span class="text-sm font-medium">Handstand Practice</span>
                                        <div class="flex space-x-2">
                                            <div class="habit-circle completed" title="Monday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle completed" title="Tuesday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle completed" title="Wednesday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle completed" title="Thursday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle completed" title="Friday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Saturday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Sunday" onclick="toggleHabit(this)"></div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Creative Practices -->
                        <div>
                            <h3 class="font-semibold text-gray-900 mb-4 flex items-center">
                                <span class="mr-2">🎨</span> Creative Practices
                            </h3>
                            <div class="space-y-4">
                                <div class="border border-gray-100 rounded-lg p-4">
                                    <div class="flex items-center justify-between mb-3">
                                        <span class="text-sm font-medium">Kora Practice</span>
                                        <div class="flex space-x-2">
                                            <div class="habit-circle completed" title="Monday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle completed" title="Tuesday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Wednesday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle completed" title="Thursday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle completed" title="Friday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Saturday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Sunday" onclick="toggleHabit(this)"></div>
                                        </div>
                                    </div>
                                </div>
                                <div class="border border-gray-100 rounded-lg p-4">
                                    <div class="flex items-center justify-between mb-3">
                                        <span class="text-sm font-medium">Dance Practice</span>
                                        <div class="flex space-x-2">
                                            <div class="habit-circle" title="Monday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Tuesday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle completed" title="Wednesday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Thursday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle completed" title="Friday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle completed" title="Saturday" onclick="toggleHabit(this)"></div>
                                            <div class="habit-circle" title="Sunday" onclick="toggleHabit(this)"></div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Habit Insights -->
                <div class="space-y-6">
                    <div class="bg-white rounded-2xl shadow-sm border border-gray-100 p-6">
                        <h3 class="font-semibold text-deep-purple mb-4 flex items-center">
                            <span class="mr-2">📊</span> Weekly Rhythm Insights
                        </h3>
                        <div class="space-y-4">
                            <div class="p-4 bg-gradient-to-r from-green-50 to-emerald-50 rounded-lg border-l-4 border-green-500">
                                <div class="text-sm font-medium text-green-800 mb-1">Strongest Rhythm</div>
                                <div class="text-sm text-green-700">Handstand Practice - 5/7 days completed</div>
                            </div>
                            <div class="p-4 bg-gradient-to-r from-yellow-50 to-amber-50 rounded-lg border-l-4 border-yellow-500">
                                <div class="text-sm font-medium text-yellow-800 mb-1">Growing Rhythm</div>
                                <div class="text-sm text-yellow-700">Dance Practice - Building momentum</div>
                            </div>
                            <div class="p-4 bg-gradient-to-r from-blue-50 to-cyan-50 rounded-lg border-l-4 border-blue-500">
                                <div class="text-sm font-medium text-blue-800 mb-1">Focus Area</div>
                                <div class="text-sm text-blue-700">Strength Training - Opportunity for consistency</div>
                            </div>
                        </div>
                    </div>

                    <div class="bg-white rounded-2xl shadow-sm border border-gray-100 p-6">
                        <h3 class="font-semibold text-deep-purple mb-4 flex items-center">
                            <span class="mr-2">🌱</span> Rhythm Reflection
                        </h3>
                        <textarea class="w-full p-3 border border-gray-200 rounded-lg resize-none focus:ring-2 focus:ring-teal focus:border-transparent" rows="4" placeholder="What rhythms are serving my highest self? What adjustments would support my flow?"></textarea>
                    </div>
                </div>
            </div>
        </div>

        <!-- Dream Reflections Section -->
        <div id="reflection" class="section">
            <div class="bg-white rounded-2xl shadow-sm border border-gray-100 p-6 mb-6">
                <h2 class="text-2xl font-bold heading-font text-deep-purple mb-6">Dream Reflections & Integration</h2>
                
                <div class="grid lg:grid-cols-2 gap-8">
                    <div class="space-y-6">
                        <div class="p-6 bg-gradient-to-br from-deep-purple/10 to-teal/10 rounded-xl border-l-4 border-deep-purple">
                            <h3 class="font-semibold text-deep-purple mb-4 flex items-center">
                                <span class="mr-2">🌙</span> Last Night's Dream
                            </h3>
                            <textarea class="w-full p-3 border border-gray-200 rounded-lg resize-none focus:ring-2 focus:ring-deep-purple focus:border-transparent" rows="4" placeholder="Describe your dream in as much detail as you remember..."></textarea>
                        </div>

                        <div class="p-6 bg-gradient-to-br from-gold/10 to-teal/10 rounded-xl border-l-4 border-gold">
                            <h3 class="font-semibold text-deep-purple mb-4 flex items-center">
                                <span class="mr-2">🔍</span> Dream Symbols Present
                            </h3>
                            <div class="grid grid-cols-2 gap-2 mb-4">
                                <label class="flex items-center space-x-2">
                                    <input type="checkbox" class="w-4 h-4 text-gold rounded">
                                    <span class="text-sm">🛡️ Safety</span>
                                </label>
                                <label class="flex items-center space-x-2">
                                    <input type="checkbox" class="w-4 h-4 text-gold rounded">
                                    <span class="text-sm">⏰ Timing</span>
                                </label>
                                <label class="flex items-center space-x-2">
                                    <input type="checkbox" class="w-4 h-4 text-gold rounded">
                                    <span class="text-sm">💝 Intimacy</span>
                                </label>
                                <label class="flex items-center space-x-2">
                                    <input type="checkbox" class="w-4 h-4 text-gold rounded">
                                    <span class="text-sm">🔄 Reciprocity</span>
                                </label>
                                <label class="flex items-center space-x-2">
                                    <input type="checkbox" class="w-4 h-4 text-gold rounded">
                                    <span class="text-sm">🔮 Clarity</span>
                                </label>
                                <label class="flex items-center space-x-2">
                                    <input type="checkbox" class="w-4 h-4 text-gold rounded">
                                    <span class="text-sm">⚔️ Discipline</span>
                                </label>
                            </div>
                            <textarea class="w-full p-3 border border-gray-200 rounded-lg resize-none focus:ring-2 focus:ring-gold focus:border-transparent" rows="2" placeholder="Other symbols or themes you noticed..."></textarea>
                        </div>
                    </div>

                    <div class="space-y-6">
                        <div class="p-6 bg-gradient-to-br from-teal/10 to-green/10 rounded-xl border-l-4 border-teal">
                            <h3 class="font-semibold text-deep-purple mb-4 flex items-center">
                                <span class="mr-2">💡</span> Dream Message & Insights
                            </h3>
                            <textarea class="w-full p-3 border border-gray-200 rounded-lg resize-none focus:ring-2 focus:ring-teal focus:border-transparent" rows="4" placeholder="What is this dream trying to tell you? What insights are emerging?"></textarea>
                        </div>

                        <div class="p-6 bg-gradient-to-br from-green/10 to-blue/10 rounded-xl border-l-4 border-green-500">
                            <h3 class="font-semibold text-deep-purple mb-4 flex items-center">
                                <span class="mr-2">🎯</span> Integration Actions
                            </h3>
                            <textarea class="w-full p-3 border border-gray-200 rounded-lg resize-none focus:ring-2 focus:ring-green-500 focus:border-transparent" rows="4" placeholder="How can you integrate this dream's wisdom into your waking life? What actions feel aligned?"></textarea>
                        </div>

                        <div class="p-6 bg-gradient-to-br from-purple-50 to-pink-50 rounded-xl border-l-4 border-purple-500">
                            <h3 class="font-semibold text-deep-purple mb-4 flex items-center">
                                <span class="mr-2">🌟</span> Gratitude & Closing
                            </h3>
                            <textarea class="w-full p-3 border border-gray-200 rounded-lg resize-none focus:ring-2 focus:ring-purple-500 focus:border-transparent" rows="3" placeholder="What are you grateful for from this dream experience?"></textarea>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Dream Pattern Tracking -->
            <div class="bg-white rounded-2xl shadow-sm border border-gray-100 p-6">
                <h3 class="text-xl font-semibold heading-font text-deep-purple mb-6">Dream Pattern Insights</h3>
                
                <div class="grid md:grid-cols-3 gap-6">
                    <div class="p-4 bg-gradient-to-br from-deep-purple/10 to-purple-100 rounded-xl text-center">
                        <div class="text-2xl mb-2">🌙</div>
                        <div class="font-medium text-sm text-deep-purple">Dreams This Week</div>
                        <div class="text-2xl font-bold text-deep-purple">5</div>
                        <div class="text-xs text-gray-600 mt-1">Remembered & recorded</div>
                    </div>
                    
                    <div class="p-4 bg-gradient-to-br from-gold/20 to-yellow-100 rounded-xl text-center">
                        <div class="text-2xl mb-2">🔄</div>
                        <div class="font-medium text-sm text-gold">Recurring Theme</div>
                        <div class="text-lg font-bold text-gold">Reciprocity</div>
                        <div class="text-xs text-gray-600 mt-1">Appeared 3 times</div>
                    </div>
                    
                    <div class="p-4 bg-gradient-to-br from-teal/20 to-cyan-100 rounded-xl text-center">
                        <div class="text-2xl mb-2">💡</div>
                        <div class="font-medium text-sm text-teal">Integration Rate</div>
                        <div class="text-2xl font-bold text-teal">80%</div>
                        <div class="text-xs text-gray-600 mt-1">Actions taken</div>
                    </div>
                </div>
            </div>
        </div>
    </main>

    <script>
        // Navigation functionality
        function showSection(sectionId) {
            // Hide all sections
            document.querySelectorAll('.section').forEach(section => {
                section.classList.remove('active');
            });
            
            // Remove active class from all tabs
            document.querySelectorAll('.nav-tab').forEach(tab => {
                tab.classList.remove('active');
            });
            
            // Show selected section
            document.getElementById(sectionId).classList.add('active');
            
            // Add active class to clicked tab
            event.target.classList.add('active');
        }

        // Habit tracking functionality
        function toggleHabit(element) {
            element.classList.toggle('completed');
        }

        // Energy level functionality
        function setEnergyLevel(type, level) {
            const dots = document.querySelectorAll(`[data-type="${type}"]`);
            dots.forEach((dot, index) => {
                if (index < level) {
                    dot.classList.remove('bg-gray-200');
                    if (type === 'physical') dot.classList.add('bg-teal');
                    if (type === 'mental') dot.classList.add('bg-gold');
                    if (type === 'creative') dot.classList.add('bg-deep-purple');
                    if (type === 'emotional') dot.classList.add('bg-green-500');
                } else {
                    dot.classList.add('bg-gray-200');
                    dot.classList.remove('bg-teal', 'bg-gold', 'bg-deep-purple', 'bg-green-500');
                }
            });
            
            // Update energy text
            const energyTexts = ['Low', 'Moderate', 'Good', 'High', 'Peak'];
            const textElement = document.getElementById(`${type}-energy-text`);
            if (textElement) {
                textElement.textContent = energyTexts[level - 1];
            }
            
            updateEnergyRecommendation();
        }

        function updateEnergyRecommendation() {
            const recommendation = document.getElementById('energy-recommendation-text');
            if (recommendation) {
                recommendation.textContent = "Perfect for high-impact creative work! Consider recording content, deep writing, or transformational client sessions.";
            }
        }

        // Initialize the app
        document.addEventListener('DOMContentLoaded', function() {
            console.log('CEO-Healer-Artist Life Planner loaded successfully!');
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9811d6af1743ad54',t:'MTc1ODIwODk0NC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
