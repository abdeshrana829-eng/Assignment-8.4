1. Project structure
Create two files:


text
Assignment-8.4/
│
├── index.html
└── style.css
2. HTML code — index.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard - Assignment 8.4</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="dashboard">

        <!-- Header -->
        <header class="header">
            <h2>My Dashboard</h2>
            <div class="profile">
                <span>Welcome, Admin</span>
                <img src="https://i.pravatar.cc/40" alt="Profile">
            </div>
        </header>

        <!-- Sidebar -->
        <aside class="sidebar">
            <h2>Dashboard</h2>
            <nav>
                <a href="#">🏠 Home</a>
                <a href="#">📊 Analytics</a>
                <a href="#">👥 Users</a>
                <a href="#">📦 Products</a>
                <a href="#">⚙️ Settings</a>
            </nav>
        </aside>

        <!-- Main Content -->
        <main class="main-content">

            <h1>Dashboard Overview</h1>
            <p class="subtitle">Welcome back! Here is your business summary.</p>

            <!-- Statistic Cards -->
            <section class="cards">

                <div class="card">
                    <div class="card-icon blue">👥</div>
                    <div class="card-info">
                        <h3>Total Users</h3>
                        <p>12,450</p>
                    </div>
                </div>

                <div class="card">
                    <div class="card-icon green">💰</div>
                    <div class="card-info">
                        <h3>Total Revenue</h3>
                        <p>$45,600</p>
                    </div>
                </div>

                <div class="card">
                    <div class="card-icon orange">📦</div>
                    <div class="card-info">
                        <h3>Total Orders</h3>
                        <p>2,350</p>
                    </div>
                </div>

                <div class="card">
                    <div class="card-icon purple">📈</div>
                    <div class="card-info">
                        <h3>Growth</h3>
                        <p>24.8%</p>
                    </div>
                </div>

            </section>

            <!-- Recent Activity -->
            <section class="activity">
                <h2>Recent Activity</h2>

                <table>
                    <thead>
                        <tr>
                            <th>Name</th>
                            <th>Activity</th>
                            <th>Date</th>
                            <th>Status</th>
                        </tr>
                    </thead>

                    <tbody>
                        <tr>
                            <td>Rahul Sharma</td>
                            <td>New Order</td>
                            <td>19 Nov 2026</td>
                            <td class="success">Completed</td>
                        </tr>

                        <tr>
                            <td>Priya Singh</td>
                            <td>New User</td>
                            <td>18 Nov 2026</td>
                            <td class="pending">Pending</td>
                        </tr>

                        <tr>
                            <td>Amit Kumar</td>
                            <td>Payment</td>
                            <td>17 Nov 2026</td>
                            <td class="success">Completed</td>
                        </tr>

                        <tr>
                            <td>Neha Verma</td>
                            <td>New Order</td>
                            <td>16 Nov 2026</td>
                            <td class="pending">Pending</td>
                        </tr>
                    </tbody>
                </table>
            </section>

        </main>

    </div>

</body>
</html>
3. CSS code — style.css

css

/* Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f4f6f9;
    color: #333;
}

/* Outer Dashboard Grid */
.dashboard {
    display: grid;
    grid-template-columns: 230px 1fr;
    grid-template-rows: 70px 1fr;
    grid-template-areas:
        "header header"
        "sidebar main";
    min-height: 100vh;
}

/* Header */
.header {
    grid-area: header;
    background-color: #ffffff;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 30px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.header h2 {
    color: #2563eb;
}

.profile {
    display: flex;
    align-items: center;
    gap: 12px;
}

.profile img {
    width: 40px;
    height: 40px;
    border-radius: 50%;
}

/* Sidebar */
.sidebar {
    grid-area: sidebar;
    background-color: #1e293b;
    color: white;
    padding: 25px 15px;
}

.sidebar h2 {
    margin-bottom: 30px;
    text-align: center;
}

.sidebar nav {
    display: flex;
    flex-direction: column;
    gap: 15px;
}

.sidebar a {
    color: white;
    text-decoration: none;
    padding: 12px;
    border-radius: 6px;
}

.sidebar a:hover {
    background-color: #334155;
}

/* Main Content */
.main-content {
    grid-area: main;
    padding: 30px;
}

.main-content h1 {
    margin-bottom: 10px;
}

.subtitle {
    color: #777;
    margin-bottom: 25px;
}

/* Statistic Cards - CSS Grid */
.cards {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
    margin-bottom: 30px;
}

/* Inner Card - Flexbox */
.card {
    background-color: white;
    padding: 25px;
    border-radius: 10px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.08);

    display: flex;
    align-items: center;
    gap: 20px;
}

.card-icon {
    width: 60px;
    height: 60px;
    border-radius: 12px;

    display: flex;
    justify-content: center;
    align-items: center;

    font-size: 28px;
}

.blue {
    background-color: #dbeafe;
}

.green {
    background-color: #dcfce7;
}

.orange {
    background-color: #ffedd5;
}

.purple {
    background-color: #f3e8ff;
}

.card-info h3 {
    color: #777;
    font-size: 15px;
    margin-bottom: 8px;
}

.card-info p {
    font-size: 25px;
    font-weight: bold;
}

/* Recent Activity */
.activity {
    background-color: white;
    padding: 25px;
    border-radius: 10px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.08);
    overflow-x: auto;
}

.activity h2 {
    margin-bottom: 20px;
}

table {
    width: 100%;
    border-collapse: collapse;
    text-align: left;
}

th, td {
    padding: 15px;
    border-bottom: 1px solid #eee;
}

th {
    background-color: #f8fafc;
}

.success {
    color: green;
    font-weight: bold;
}

.pending {
    color: orange;
    font-weight: bold;
}

/* Responsive Design */
@media (max-width: 768px) {

    .dashboard {
        grid-template-columns: 1fr;
        grid-template-rows: auto auto 1fr;
        grid-template-areas:
            "header"
            "sidebar"
            "main";
    }

    .sidebar nav {
        flex-direction: row;
        flex-wrap: wrap;
    }

    .cards {
        grid-template-columns: 1fr;
    }

    .main-content {
        padding: 20px;
    }
}

@media (max-width: 480px) {

    .header {
        padding: 12px;
    }

    .header h2 {
        font-size: 18px;
    }

    .profile span {
        display: none;
    }

    .sidebar nav {
        flex-direction: column;
    }
}
4. Expected dashboard design
GitHub - samridhiibhardwaj/Responsive-Admin-Dashboard-with-Sidebar
 
5. Concepts used in this assignment
Requirement

CSS property used

Outer dashboard layout

display: grid

Header, sidebar, main

grid-template-areas

Four statistic cards

grid-template-columns

Card alignment

display: flex

Icon and text spacing

gap

Vertical alignment

align-items: center

Responsive layout

@media

Recent activity

HTML table

6. How to check Grid using DevTools
Open index.html in Chrome.

Press F12 to open Developer Tools.

Select the Elements tab.

Find the <div class="dashboard"> element.

Click the small grid badge next to the .dashboard element in the Styles panel.

Chrome will highlight the Grid layout on the page.

You can also inspect .cards to see its inner Grid layout.