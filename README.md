<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Self-Care Sanctuary</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
            color: #333;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
        }

        header {
            text-align: center;
            color: white;
            margin-bottom: 40px;
            animation: fadeIn 1s ease-in;
        }

        h1 {
            font-size: 3em;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .tagline {
            font-size: 1.2em;
            opacity: 0.9;
        }

        .stats-dashboard {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .stat-card {
            background: white;
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            animation: slideUp 0.5s ease-out forwards;
        }

        .stat-number {
            font-size: 2.5em;
            font-weight: bold;
            color: #667eea;
        }

        .stat-label {
            color: #666;
            margin-top: 5px;
        }

        .categories {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }

        .category-card {
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            cursor: pointer;
            animation: slideUp 0.5s ease-out forwards;
            opacity: 0;
        }

        .category-card:nth-child(1) { animation-delay: 0.1s; }
        .category-card:nth-child(2) { animation-delay: 0.2s; }
        .category-card:nth-child(3) { animation-delay: 0.3s; }
        .category-card:nth-child(4) { animation-delay: 0.4s; }
        .category-card:nth-child(5) { animation-delay: 0.5s; }
        .category-card:nth-child(6) { animation-delay: 0.6s; }
        .category-card:nth-child(7) { animation-delay: 0.7s; }
        .category-card:nth-child(8) { animation-delay: 0.8s; }
        .category-card:nth-child(9) { animation-delay: 0.9s; }
        .category-card:nth-child(10) { animation-delay: 1s; }

        .category-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.3);
        }

        .category-icon {
            font-size: 3em;
            margin-bottom: 15px;
        }

        .category-card h2 {
            color: #667eea;
            margin-bottom: 15px;
            font-size: 1.5em;
        }

        .practice-list {
            list-style: none;
        }

        .practice-item {
            padding: 12px;
            margin: 8px 0;
            background: #f8f9fa;
            border-radius: 10px;
            display: flex;
            align-items: center;
            transition: all 0.3s ease;
        }

        .practice-item:hover {
            background: #e9ecef;
            transform: translateX(5px);
        }

        .practice-item input[type="checkbox"] {
            margin-right: 12px;
            width: 20px;
            height: 20px;
            cursor: pointer;
        }

        .practice-item.completed {
            opacity: 0.6;
            text-decoration: line-through;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }

        .feature-box {
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }

        .feature-box h3 {
            color: #667eea;
            margin-bottom: 15px;
            font-size: 1.3em;
        }

        .mood-tracker {
            display: flex;
            justify-content: space-around;
            margin-top: 15px;
        }

        .mood-btn {
            font-size: 2.5em;
            background: none;
            border: none;
            cursor: pointer;
            transition: transform 0.2s ease;
            opacity: 0.5;
        }

        .mood-btn:hover {
            transform: scale(1.2);
        }

        .mood-btn.selected {
            opacity: 1;
            transform: scale(1.3);
        }

        .timer-display {
            font-size: 3em;
            text-align: center;
            color: #667eea;
            margin: 20px 0;
            font-weight: bold;
        }

        .timer-controls {
            display: flex;
            gap: 10px;
            justify-content: center;
        }

        .btn {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 25px;
            font-size: 1em;
            cursor: pointer;
            transition: transform 0.3s ease;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .btn:hover {
            transform: scale(1.05);
        }

        .daily-inspiration {
            background: white;
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            margin-top: 30px;
            animation: fadeIn 1.5s ease-in;
        }

        .inspiration-quote {
            font-size: 1.5em;
            font-style: italic;
            color: #667eea;
            margin-bottom: 15px;
            transition: opacity 0.3s ease;
        }

        .refresh-btn {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            padding: 15px 30px;
            border-radius: 30px;
            font-size: 1.1em;
            cursor: pointer;
            margin-top: 20px;
            transition: transform 0.3s ease;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .refresh-btn:hover {
            transform: scale(1.05);
        }

        .progress-section {
            background: white;
            border-radius: 20px;
            padding: 30px;
            margin-top: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }

        .progress-bar {
            background: #e9ecef;
            height: 30px;
            border-radius: 15px;
            overflow: hidden;
            margin-top: 15px;
        }

        .progress-fill {
            background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
            height: 100%;
            transition: width 0.5s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
        }

        .notes-area {
            width: 100%;
            min-height: 120px;
            padding: 15px;
            border: 2px solid #e9ecef;
            border-radius: 10px;
            font-family: inherit;
            font-size: 1em;
            margin-top: 10px;
            resize: vertical;
        }

        .water-tracker {
            display: flex;
            gap: 10px;
            margin-top: 15px;
            flex-wrap: wrap;
        }

        .water-glass {
            font-size: 2em;
            cursor: pointer;
            transition: transform 0.2s ease;
            opacity: 0.3;
        }

        .water-glass.filled {
            opacity: 1;
        }

        .water-glass:hover {
            transform: scale(1.1);
        }

        .todo-item {
            padding: 15px;
            margin: 10px 0;
            background: #f8f9fa;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            transition: all 0.3s ease;
            border-left: 4px solid transparent;
        }

        .todo-item.priority-high {
            border-left-color: #dc3545;
            background: #fff5f5;
        }

        .todo-item.priority-medium {
            border-left-color: #ffc107;
            background: #fffef5;
        }

        .todo-item.priority-low {
            border-left-color: #28a745;
            background: #f5fff5;
        }

        .todo-item:hover {
            background: #e9ecef;
            transform: translateX(5px);
        }

        .todo-item.completed {
            opacity: 0.5;
        }

        .todo-item.completed .todo-text {
            text-decoration: line-through;
        }

        .todo-content {
            display: flex;
            align-items: center;
            flex: 1;
            gap: 12px;
        }

        .todo-checkbox {
            width: 22px;
            height: 22px;
            cursor: pointer;
        }

        .todo-text {
            flex: 1;
            font-size: 1em;
        }

        .priority-badge {
            padding: 4px 10px;
            border-radius: 12px;
            font-size: 0.8em;
            font-weight: bold;
            text-transform: uppercase;
        }

        .priority-badge.high {
            background: #dc3545;
            color: white;
        }

        .priority-badge.medium {
            background: #ffc107;
            color: #333;
        }

        .priority-badge.low {
            background: #28a745;
            color: white;
        }

        .todo-actions {
            display: flex;
            gap: 8px;
        }

        .delete-btn {
            background: #dc3545;
            color: white;
            border: none;
            padding: 6px 14px;
            border-radius: 6px;
            cursor: pointer;
            font-size: 0.9em;
            transition: background 0.3s ease;
        }

        .delete-btn:hover {
            background: #c82333;
        }

        .edit-btn {
            background: #667eea;
            color: white;
            border: none;
            padding: 6px 14px;
            border-radius: 6px;
            cursor: pointer;
            font-size: 0.9em;
            transition: background 0.3s ease;
        }

        .edit-btn:hover {
            background: #5568d3;
        }

        .filter-btn {
            padding: 8px 16px;
            border: 2px solid #667eea;
            background: white;
            color: #667eea;
            border-radius: 20px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 0.9em;
        }

        .filter-btn:hover {
            background: #f0f2ff;
        }

        .filter-btn.active {
            background: #667eea;
            color: white;
        }

        footer {
            text-align: center;
            color: white;
            padding: 30px;
            margin-top: 50px;
            font-size: 1em;
            opacity: 0.9;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @media (max-width: 768px) {
            h1 { font-size: 2em; }
            .categories { grid-template-columns: 1fr; }
            .features-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>🌟 Your Self-Care Sanctuary 🌟</h1>
            <p class="tagline">Small steps, big impact. Take care of yourself today.</p>
        </header>

        <div class="stats-dashboard">
            <div class="stat-card">
                <div class="stat-number" id="today-completed">0</div>
                <div class="stat-label">Completed Today ✅</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" id="wellness-score">0%</div>
                <div class="stat-label">Wellness Score 💯</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" id="todo-count">0</div>
                <div class="stat-label">Tasks Pending 📋</div>
            </div>
        </div>

        <div class="categories">
            <div class="category-card">
                <div class="category-icon">🧘‍♀️</div>
                <h2>Mindfulness</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>5-minute morning meditation</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Deep breathing exercise</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Evening gratitude journal</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Practice mindful eating</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">💪</div>
                <h2>Physical Wellness</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>20-minute walk or exercise</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Stretch for 10 minutes</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Drink 8 glasses of water</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Take the stairs today</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">😴</div>
                <h2>Rest & Recovery</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>7-8 hours of sleep</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Screen-free hour before bed</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Take a power nap (15-20 min)</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Create a calming bedtime routine</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">💚</div>
                <h2>Emotional Care</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Call a friend or loved one</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Say "no" to something draining</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Do something that makes you laugh</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Write down 3 things you're grateful for</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">🎨</div>
                <h2>Creative Joy</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>15 minutes of a hobby you love</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Listen to your favorite music</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Try something new and fun</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Doodle or color for relaxation</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">🍎</div>
                <h2>Nourishment</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Eat a colorful, balanced meal</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Prepare food mindfully</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Limit caffeine after 2 PM</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Include fruits/veggies in meals</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">🌱</div>
                <h2>Personal Growth</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Read for 20 minutes</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Learn something new</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Practice positive affirmations</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Set intentions for tomorrow</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">🌿</div>
                <h2>Nature Connection</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Spend 15 minutes outdoors</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Water your plants</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Watch sunrise or sunset</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Practice grounding/earthing</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">🧹</div>
                <h2>Environment</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Declutter one small area</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Make your bed</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Create a cozy space</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Light a candle or diffuse oils</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">👥</div>
                <h2>Social Wellness</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Send a kind message to someone</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Have a meaningful conversation</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Practice active listening</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Set healthy boundaries</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">💰</div>
                <h2>Financial Wellness</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Review your budget</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Save a small amount today</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Track your expenses</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Avoid impulse purchases</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">🎓</div>
                <h2>Intellectual Wellness</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Watch an educational video</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Practice a new skill</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Solve a puzzle or brain teaser</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Engage in critical thinking</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">✨</div>
                <h2>Spiritual Wellness</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Practice mindfulness or prayer</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Reflect on your values</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Connect with something bigger</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Practice gratitude meditation</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">💼</div>
                <h2>Career Wellness</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Set a career goal for today</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Update your skills/resume</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Network with a colleague</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Celebrate a work achievement</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">🎮</div>
                <h2>Fun & Play</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Play a game or sport</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Watch something that makes you laugh</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Try something spontaneous</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Dance or sing freely</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">🛡️</div>
                <h2>Safety & Security</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Check your home security</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Review emergency contacts</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Practice digital safety</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Ensure you feel safe & secure</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">❤️</div>
                <h2>Romantic Wellness</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Express appreciation to partner</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Plan quality time together</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Practice self-love</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Communicate openly & honestly</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">🐾</div>
                <h2>Pet Care</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Spend quality time with pet</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Play or exercise with pet</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Groom or care for pet</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Check pet's health & happiness</span>
                    </li>
                </ul>
            </div>

            <div class="category-card">
                <div class="category-icon">📱</div>
                <h2>Digital Wellness</h2>
                <ul class="practice-list">
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Take a social media break</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Limit screen time</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Unsubscribe from negative content</span>
                    </li>
                    <li class="practice-item">
                        <input type="checkbox" onchange="updateProgress()">
                        <span>Practice mindful tech use</span>
                    </li>
                </ul>
            </div>
        </div>

        <div class="features-grid">
            <div class="feature-box">
                <h3>🎯 Meditation Timer</h3>
                <div class="timer-display" id="timer">05:00</div>
                <div class="timer-controls">
                    <button class="btn" onclick="startTimer()">Start</button>
                    <button class="btn" onclick="pauseTimer()">Pause</button>
                    <button class="btn" onclick="resetTimer()">Reset</button>
                </div>
            </div>

            <div class="feature-box">
                <h3>😊 Today's Mood</h3>
                <p>How are you feeling right now?</p>
                <div class="mood-tracker">
                    <button class="mood-btn" onclick="selectMood(this)">😢</button>
                    <button class="mood-btn" onclick="selectMood(this)">😕</button>
                    <button class="mood-btn" onclick="selectMood(this)">😐</button>
                    <button class="mood-btn" onclick="selectMood(this)">😊</button>
                    <button class="mood-btn" onclick="selectMood(this)">😄</button>
                </div>
            </div>

            <div class="feature-box">
                <h3>💧 Water Intake</h3>
                <p>Track your daily water consumption</p>
                <div class="water-tracker" id="water-tracker">
                    <span class="water-glass" onclick="toggleWater(this)">💧</span>
                    <span class="water-glass" onclick="toggleWater(this)">💧</span>
                    <span class="water-glass" onclick="toggleWater(this)">💧</span>
                    <span class="water-glass" onclick="toggleWater(this)">💧</span>
                    <span class="water-glass" onclick="toggleWater(this)">💧</span>
                    <span class="water-glass" onclick="toggleWater(this)">💧</span>
                    <span class="water-glass" onclick="toggleWater(this)">💧</span>
                    <span class="water-glass" onclick="toggleWater(this)">💧</span>
                </div>
            </div>

            <div class="feature-box">
                <h3>📝 Daily Reflection</h3>
                <p>What went well today? What could be better?</p>
                <textarea class="notes-area" placeholder="Write your thoughts here..." id="daily-notes"></textarea>
            </div>

            <div class="feature-box">
                <h3>✅ Personal To-Do List</h3>
                <p>Organize your tasks by priority and stay productive</p>
                <div style="display: flex; gap: 10px; margin-top: 15px;">
                    <input type="text" id="todo-input" placeholder="What do you need to do?" 
                           style="flex: 1; padding: 14px; border: 2px solid #e9ecef; border-radius: 10px; font-size: 1em;"
                           onkeypress="if(event.key === 'Enter') addTodo()">
                    <select id="priority-select" style="padding: 14px; border: 2px solid #e9ecef; border-radius: 10px; font-size: 1em;">
                        <option value="low">Low</option>
                        <option value="medium" selected>Medium</option>
                        <option value="high">High</option>
                    </select>
                    <button class="btn" onclick="addTodo()">Add Task</button>
                </div>
                
                <div style="margin-top: 20px;">
                    <div style="display: flex; gap: 10px; margin-bottom: 15px;">
                        <button class="filter-btn active" onclick="filterTodos('all')">All</button>
                        <button class="filter-btn" onclick="filterTodos('active')">Active</button>
                        <button class="filter-btn" onclick="filterTodos('completed')">Completed</button>
                    </div>
                    
                    <ul id="todo-list" style="list-style: none; margin-top: 15px; max-height: 400px; overflow-y: auto;"></ul>
                    
                    <div style="margin-top: 15px; text-align: center; color: #666; font-size: 0.9em;">
                        <span id="pending-tasks">0 tasks remaining</span>
                    </div>
                </div>
            </div>
        </div>

        <div class="progress-section">
            <h2>Today's Progress</h2>
            <p>You've completed <span id="completed-count">0</span> out of <span id="total-count">80</span> practices!</p>
            <div class="progress-bar">
                <div class="progress-fill" id="progress-fill">0%</div>
            </div>
        </div>

        <div class="daily-inspiration">
            <h2>Daily Inspiration</h2>
            <p class="inspiration-quote" id="quote">
                "Self-care is not selfish. You cannot serve from an empty vessel."
            </p>
            <p id="quote-author"><em>— Eleanor Brown</em></p>
            <button class="refresh-btn" onclick="newQuote()">Get New Inspiration ✨</button>
        </div>

        <footer>
            <p>All rights are reserved by VINAY KUMAWAT</p>
        </footer>
    </div>

    <script>
        const quotes = [
            { text: "Self-care is not selfish. You cannot serve from an empty vessel.", author: "Eleanor Brown" },
            { text: "Almost everything will work again if you unplug it for a few minutes, including you.", author: "Anne Lamott" },
            { text: "You yourself, as much as anybody in the entire universe, deserve your love and affection.", author: "Buddha" },
            { text: "Rest and self-care are so important. When you take time to replenish your spirit, it allows you to serve others from the overflow.", author: "Eleanor Brownn" },
            { text: "Caring for myself is not self-indulgence, it is self-preservation.", author: "Audre Lorde" },
            { text: "When you recover or discover something that nourishes your soul and brings joy, care enough about yourself to make room for it in your life.", author: "Jean Shinoda Bolen" },
            { text: "It's not selfish to love yourself, take care of yourself, and to make your happiness a priority. It's necessary.", author: "Mandy Hale" },
            { text: "Talk to yourself like you would to someone you love.", author: "Brené Brown" },
            { text: "Nourishing yourself in a way that helps you blossom in the direction you want to go is attainable, and you are worth the effort.", author: "Deborah Day" },
            { text: "Be gentle with yourself. You're doing the best you can.", author: "Unknown" }
        ];

        let timerInterval;
        let timeLeft = 300;
        let timerRunning = false;

        function newQuote() {
            const quoteEl = document.getElementById('quote');
            const authorEl = document.getElementById('quote-author');
            const randomQuote = quotes[Math.floor(Math.random() * quotes.length)];
            quoteEl.style.opacity = '0';
            setTimeout(() => {
                quoteEl.textContent = randomQuote.text;
                authorEl.innerHTML = `<em>— ${randomQuote.author}</em>`;
                quoteEl.style.opacity = '1';
            }, 300);
        }

        function updateProgress() {
            const checkboxes = document.querySelectorAll('input[type="checkbox"]');
            const checked = document.querySelectorAll('input[type="checkbox"]:checked');
            const total = checkboxes.length;
            const completed = checked.length;
            const percentage = Math.round((completed / total) * 100);

            document.getElementById('completed-count').textContent = completed;
            document.getElementById('total-count').textContent = total;
            document.getElementById('progress-fill').style.width = percentage + '%';
            document.getElementById('progress-fill').textContent = percentage + '%';
            
            document.getElementById('today-completed').textContent = completed;
            document.getElementById('wellness-score').textContent = percentage + '%';

            checkboxes.forEach(checkbox => {
                if (checkbox.checked) {
                    checkbox.parentElement.classList.add('completed');
                } else {
                    checkbox.parentElement.classList.remove('completed');
                }
            });
        }

        function selectMood(btn) {
            document.querySelectorAll('.mood-btn').forEach(b => b.classList.remove('selected'));
            btn.classList.add('selected');
        }

        function toggleWater(glass) {
            glass.classList.toggle('filled');
        }

        function startTimer() {
            if (!timerRunning) {
                timerRunning = true;
                timerInterval = setInterval(() => {
                    if (timeLeft > 0) {
                        timeLeft--;
                        updateTimerDisplay();
                    } else {
                        pauseTimer();
                        alert('Meditation complete! Great job! 🎉');
                    }
                }, 1000);
            }
        }

        function pauseTimer() {
            timerRunning = false;
            clearInterval(timerInterval);
        }

        function resetTimer() {
            pauseTimer();
            timeLeft = 300;
            updateTimerDisplay();
        }

        function updateTimerDisplay() {
            const minutes = Math.floor(timeLeft / 60);
            const seconds = timeLeft % 60;
            document.getElementById('timer').textContent = 
                `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
        }

        document.getElementById('quote').style.transition = 'opacity 0.3s ease';

        // To-Do List functionality
        let todos = [];
        let currentFilter = 'all';

        function addTodo() {
            const input = document.getElementById('todo-input');
            const priority = document.getElementById('priority-select').value;
            const text = input.value.trim();
            
            if (text) {
                const todo = {
                    id: Date.now(),
                    text: text,
                    completed: false,
                    priority: priority
                };
                todos.unshift(todo);
                input.value = '';
                renderTodos();
                updateTodoStats();
            }
        }

        function toggleTodo(id) {
            const todo = todos.find(t => t.id === id);
            if (todo) {
                todo.completed = !todo.completed;
                renderTodos();
                updateTodoStats();
            }
        }

        function deleteTodo(id) {
            todos = todos.filter(t => t.id !== id);
            renderTodos();
            updateTodoStats();
        }

        function editTodo(id) {
            const todo = todos.find(t => t.id === id);
            if (todo) {
                const newText = prompt('Edit task:', todo.text);
                if (newText && newText.trim()) {
                    todo.text = newText.trim();
                    renderTodos();
                }
            }
        }

        function filterTodos(filter) {
            currentFilter = filter;
            document.querySelectorAll('.filter-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            event.target.classList.add('active');
            renderTodos();
        }

        function renderTodos() {
            const list = document.getElementById('todo-list');
            list.innerHTML = '';
            
            let filteredTodos = todos;
            if (currentFilter === 'active') {
                filteredTodos = todos.filter(t => !t.completed);
            } else if (currentFilter === 'completed') {
                filteredTodos = todos.filter(t => t.completed);
            }

            if (filteredTodos.length === 0) {
                list.innerHTML = '<li style="text-align: center; color: #999; padding: 30px;">No tasks to show</li>';
                return;
            }
            
            filteredTodos.forEach(todo => {
                const li = document.createElement('li');
                li.className = `todo-item priority-${todo.priority}${todo.completed ? ' completed' : ''}`;
                li.innerHTML = `
                    <div class="todo-content">
                        <input type="checkbox" class="todo-checkbox" ${todo.completed ? 'checked' : ''} 
                               onchange="toggleTodo(${todo.id})">
                        <span class="todo-text">${todo.text}</span>
                        <span class="priority-badge ${todo.priority}">${todo.priority}</span>
                    </div>
                    <div class="todo-actions">
                        <button class="edit-btn" onclick="editTodo(${todo.id})">Edit</button>
                        <button class="delete-btn" onclick="deleteTodo(${todo.id})">Delete</button>
                    </div>
                `;
                list.appendChild(li);
            });
        }

        function updateTodoStats() {
            const pending = todos.filter(t => !t.completed).length;
            document.getElementById('todo-count').textContent = pending;
            document.getElementById('pending-tasks').textContent = 
                `${pending} task${pending !== 1 ? 's' : ''} remaining`;
        }

        updateTodoStats();
    </script>
</body>
</html>
