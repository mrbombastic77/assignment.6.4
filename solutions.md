HTML
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Positioning Practice</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <!-- Sticky Navigation Bar -->
    <nav class="sticky-nav">
        <div class="nav-brand">Coders Club</div>
        <ul class="nav-links">
            <li><a href="#about">About</a></li>
            <li><a href="#features">Features</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <!-- Main Content Sections -->
    <main class="container">
        <section id="about" class="section">
            <h2>About Positioning</h2>
            <p>This page demonstrates various CSS positioning techniques, including static, relative, absolute, fixed, and sticky positioning, along with z-index layering.</p>
        </section>

        <section id="features" class="section">
            <h2>Featured Projects & Badges</h2>
            <div class="card-grid">
                <!-- Card with Absolute Positioned Badge -->
                <div class="card">
                    <span class="badge">New</span>
                    <h3>Web Development Portfolio</h3>
                    <p>A fully responsive portfolio built using semantic HTML and custom CSS design tokens.</p>
                </div>
                <div class="card">
                    <span class="badge featured-badge">Popular</span>
                    <h3>JavaScript Calculator</h3>
                    <p>An interactive browser application for performing arithmetic computations and handling events.</p>
                </div>
            </div>
        </section>

        <section id="contact" class="section">
            <h2>Contact Information</h2>
            <p>Reach out to us for workshops, tech events, and collaborative programming projects.</p>
        </section>
    </main>

    <!-- Floating Action Button (Fixed Position) -->
    <button class="fab" aria-label="Help or Contact">💬</button>

    <footer>
        <p>&copy; 2026 Atim Akhtar. All rights reserved.</p>
    </footer>
</body>
</html>
CSS
/* style.css */
body {
    font-family: Arial, sans-serif;
    background-color: #f8fafc;
    color: #334155;
    margin: 0;
    padding: 0;
    line-height: 1.6;
}

/* 2. Sticky Navigation Bar */
.sticky-nav {
    position: sticky;
    top: 0;
    background-color: #0f172a;
    color: #ffffff;
    padding: 1rem 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 1000;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.nav-brand {
    font-weight: bold;
    font-size: 1.25rem;
}

.nav-links {
    list-style: none;
    display: flex;
    gap: 1.5rem;
    margin: 0;
    padding: 0;
}

.nav-links a {
    color: #ffffff;
    text-decoration: none;
    font-weight: 500;
    transition: color 0.2s ease;
}

.nav-links a:hover {
    color: #38bdf8;
}

/* Container & Sections */
.container {
    max-width: 800px;
    margin: 2rem auto;
    padding: 0 1rem;
    display: flex;
    flex-direction: column;
    gap: 2rem;
}

.section {
    background-color: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 10px;
    padding: 2rem;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
}

.section h2 {
    color: #0f172a;
    margin-top: 0;
    margin-bottom: 1rem;
    border-bottom: 2px solid #e2e8f0;
    padding-bottom: 0.5rem;
}

/* Card & Absolute Badge Positioning */
.card-grid {
    display: flex;
    gap: 1.5rem;
    flex-wrap: wrap;
}

.card {
    /* 5. Relative positioning applied to parent so absolute children align relative to this card */
    position: relative;
    background-color: #f8fafc;
    border: 1px solid #cbd5e1;
    border-radius: 8px;
    padding: 1.5rem;
    flex: 1;
    min-width: 250px;
}

.card h3 {
    margin-top: 0;
    color: #0f172a;
}

/* 4. Absolute Positioning for Badge */
.badge {
    position: absolute;
    top: 15px;
    right: 15px;
    background-color: #0284c7;
    color: #ffffff;
    font-size: 0.75rem;
    font-weight: bold;
    padding: 4px 8px;
    border-radius: 4px;
    text-transform: uppercase;
}

.featured-badge {
    background-color: #10b981;
}

/* 3. Fixed Floating Action Button (FAB) */
.fab {
    position: fixed;
    bottom: 30px;
    right: 30px;
    background-color: #0284c7;
    color: #ffffff;
    border: none;
    border-radius: 50%;
    width: 60px;
    height: 60px;
    font-size: 1.5rem;
    cursor: pointer;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.15);
    display: flex;
    justify-content: center;
    align-items: center;
    /* 6. z-index controls stacking order over page content */
    z-index: 999;
    transition: background-color 0.2s ease, transform 0.2s ease;
}

.fab:hover {
    background-color: #0369a1;
    transform: scale(1.05);
}

footer {
    text-align: center;
    padding: 1.5rem;
    color: #64748b;
    font-size: 0.875rem;
    border-top: 1px solid #e2e8f0;
    margin-top: 3rem;
}