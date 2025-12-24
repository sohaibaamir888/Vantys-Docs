<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vantys Docs</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            background: linear-gradient(135deg, #f5f5f5 0%, #ffffff 50%, #f8f8f8 100%);
            color: #1a1a1a;
            line-height: 1.6;
            min-height: 100vh;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #ffffff 0%, #fafafa 100%);
            border-bottom: 1px solid #e5e5e5;
            padding: 1.5rem 2rem;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
        }

        .header-content {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 600;
            color: #0d47a1;
        }

        .menu-toggle {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: #666;
        }

        /* Main Container */
        .container {
            display: flex;
            max-width: 1400px;
            margin: 0 auto;
            gap: 2rem;
            padding: 2rem;
            min-height: calc(100vh - 80px);
        }

        /* Left Sidebar Navigation */
        .sidebar {
            width: 280px;
            background: #ffffff;
            border-radius: 8px;
            border: 1px solid #e5e5e5;
            padding: 1.5rem;
            height: fit-content;
            position: sticky;
            top: 100px;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: all 0.3s ease;
        }

        .sidebar.collapsed {
            width: 60px;
        }

        .sidebar.collapsed .nav-label {
            display: none;
        }

        .sidebar.collapsed .nav-item span {
            display: none;
        }

        .sidebar-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #e5e5e5;
        }

        .nav-label {
            font-size: 0.875rem;
            font-weight: 600;
            text-transform: uppercase;
            color: #666;
            letter-spacing: 0.5px;
            transition: opacity 0.3s ease;
        }

        .toggle-btn {
            background: none;
            border: none;
            font-size: 1.2rem;
            cursor: pointer;
            color: #999;
            padding: 0.25rem;
            border-radius: 4px;
            transition: all 0.3s ease;
        }

        .toggle-btn:hover {
            background-color: #f0f0f0;
            color: #333;
        }

        nav ul {
            list-style: none;
        }

        nav li {
            margin-bottom: 0.5rem;
        }

        .nav-item {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            padding: 0.75rem 1rem;
            border-radius: 6px;
            cursor: pointer;
            transition: all 0.2s ease;
            color: #666;
            text-decoration: none;
            font-size: 0.95rem;
            user-select: none;
        }

        .nav-item:hover {
            background-color: #f5f5f5;
            color: #0d47a1;
        }

        .nav-item.active {
            background-color: #e3f2fd;
            color: #0d47a1;
            font-weight: 500;
        }

        .nav-item-icon {
            font-size: 1.1rem;
            flex-shrink: 0;
            width: 20px;
            text-align: center;
        }

        .submenu {
            display: none;
            list-style: none;
            margin-top: 0.5rem;
            padding-left: 2.25rem;
        }

        .submenu.open {
            display: block;
        }

        .submenu li {
            margin-bottom: 0.35rem;
        }

        .submenu-item {
            padding: 0.5rem 0.75rem;
            font-size: 0.85rem;
            color: #999;
            transition: all 0.2s ease;
        }

        .submenu-item:hover {
            color: #0d47a1;
        }

        /* Main Content */
        .main-content {
            flex: 1;
            background: #ffffff;
            border-radius: 8px;
            border: 1px solid #e5e5e5;
            padding: 2.5rem;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
        }

        h1 {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: #0d47a1;
        }

        h2 {
            font-size: 1.75rem;
            font-weight: 600;
            margin-top: 2rem;
            margin-bottom: 1rem;
            color: #1a1a1a;
        }

        h3 {
            font-size: 1.25rem;
            font-weight: 600;
            margin-top: 1.5rem;
            margin-bottom: 0.75rem;
            color: #1a1a1a;
        }

        p {
            margin-bottom: 1rem;
            color: #666;
        }

        code {
            background: #f5f5f5;
            padding: 0.2rem 0.4rem;
            border-radius: 3px;
            font-family: 'Monaco', 'Courier New', monospace;
            font-size: 0.9em;
            color: #d73a49;
        }

        pre {
            background: #1e1e1e;
            color: #e0e0e0;
            padding: 1.5rem;
            border-radius: 6px;
            overflow-x: auto;
            margin-bottom: 1.5rem;
            font-family: 'Monaco', 'Courier New', monospace;
            font-size: 0.85rem;
            line-height: 1.5;
        }

        pre code {
            background: none;
            color: #e0e0e0;
            padding: 0;
            border-radius: 0;
        }

        a {
            color: #0d47a1;
            text-decoration: none;
            border-bottom: 1px solid transparent;
            transition: all 0.2s ease;
        }

        a:hover {
            border-bottom-color: #0d47a1;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .container {
                flex-direction: column;
                gap: 1rem;
            }

            .sidebar {
                width: 100%;
                position: static;
                margin-bottom: 1rem;
            }

            .sidebar.collapsed {
                width: 100%;
            }

            .sidebar.collapsed .nav-label {
                display: inline;
            }

            .sidebar.collapsed .nav-item span {
                display: inline;
            }

            .main-content {
                padding: 1.5rem;
            }

            h1 {
                font-size: 2rem;
            }

            h2 {
                font-size: 1.5rem;
            }

            .menu-toggle {
                display: block;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="header-content">
            <div class="logo">Vantys Docs</div>
            <button class="menu-toggle" id="mobileMenuToggle">☰</button>
        </div>
    </header>

    <div class="container">
        <aside class="sidebar" id="sidebar">
            <div class="sidebar-header">
                <span class="nav-label">Navigation</span>
                <button class="toggle-btn" id="sidebarToggle" title="Toggle sidebar">«</button>
            </div>
            <nav>
                <ul>
                    <li>
                        <a href="#" class="nav-item active">
                            <span class="nav-item-icon">🏠</span>
                            <span>Home</span>
                        </a>
                    </li>
                    <li>
                        <a href="#" class="nav-item" onclick="toggleSubmenu(event, this)">
                            <span class="nav-item-icon">📚</span>
                            <span>Getting Started</span>
                        </a>
                        <ul class="submenu">
                            <li><a href="#" class="submenu-item">Installation</a></li>
                            <li><a href="#" class="submenu-item">Configuration</a></li>
                            <li><a href="#" class="submenu-item">First Steps</a></li>
                        </ul>
                    </li>
                    <li>
                        <a href="#" class="nav-item" onclick="toggleSubmenu(event, this)">
                            <span class="nav-item-icon">⚙️</span>
                            <span>API Reference</span>
                        </a>
                        <ul class="submenu">
                            <li><a href="#" class="submenu-item">Authentication</a></li>
                            <li><a href="#" class="submenu-item">Endpoints</a></li>
                            <li><a href="#" class="submenu-item">Status Codes</a></li>
                        </ul>
                    </li>
                    <li>
                        <a href="#" class="nav-item" onclick="toggleSubmenu(event, this)">
                            <span class="nav-item-icon">🔧</span>
                            <span>Guides</span>
                        </a>
                        <ul class="submenu">
                            <li><a href="#" class="submenu-item">Tutorials</a></li>
                            <li><a href="#" class="submenu-item">Best Practices</a></li>
                            <li><a href="#" class="submenu-item">Examples</a></li>
                        </ul>
                    </li>
                    <li>
                        <a href="#" class="nav-item">
                            <span class="nav-item-icon">❓</span>
                            <span>FAQ</span>
                        </a>
                    </li>
                    <li>
                        <a href="#" class="nav-item">
                            <span class="nav-item-icon">📞</span>
                            <span>Support</span>
                        </a>
                    </li>
                </ul>
            </nav>
        </aside>

        <main class="main-content">
            <h1>Welcome to Vantys Documentation</h1>
            <p>Comprehensive guides and documentation for the Vantys platform. Get started quickly with our easy-to-follow tutorials and detailed API reference.</p>

            <h2>What is Vantys?</h2>
            <p>Vantys is a powerful, modern platform designed to help you build amazing applications with ease. Our documentation covers everything you need to know to get started and become an expert.</p>

            <h2>Quick Start</h2>
            <p>Get up and running in minutes with our quick start guide:</p>
            <pre><code>npm install vantys
import Vantys from 'vantys';

const vantys = new Vantys({
    apiKey: 'your-api-key'
});

// You're ready to go!
vantys.connect();</code></pre>

            <h2>Key Features</h2>
            <ul style="margin-left: 1.5rem; margin-bottom: 1.5rem;">
                <li style="margin-bottom: 0.5rem;"><strong>Easy Integration</strong> - Simple API for quick integration</li>
                <li style="margin-bottom: 0.5rem;"><strong>Scalability</strong> - Built to scale with your needs</li>
                <li style="margin-bottom: 0.5rem;"><strong>Real-time</strong> - Real-time updates and notifications</li>
                <li style="margin-bottom: 0.5rem;"><strong>Security</strong> - Enterprise-grade security features</li>
            </ul>

            <h2>Documentation Sections</h2>
            <p>Browse through our documentation using the navigation menu on the left:</p>
            <ul style="margin-left: 1.5rem; margin-bottom: 1.5rem;">
                <li style="margin-bottom: 0.5rem;"><strong>Getting Started</strong> - Installation and initial setup</li>
                <li style="margin-bottom: 0.5rem;"><strong>API Reference</strong> - Complete API documentation</li>
                <li style="margin-bottom: 0.5rem;"><strong>Guides</strong> - Tutorials and best practices</li>
                <li style="margin-bottom: 0.5rem;"><strong>FAQ</strong> - Frequently asked questions</li>
            </ul>

            <h2>Need Help?</h2>
            <p>If you can't find what you're looking for, feel free to reach out to our support team at <a href="mailto:support@vantys.com">support@vantys.com</a> or visit our <a href="#">support page</a>.</p>
        </main>
    </div>

    <script>
        const sidebarToggle = document.getElementById('sidebarToggle');
        const sidebar = document.getElementById('sidebar');
        const mobileMenuToggle = document.getElementById('mobileMenuToggle');

        // Toggle sidebar collapse
        sidebarToggle.addEventListener('click', () => {
            sidebar.classList.toggle('collapsed');
            sidebarToggle.textContent = sidebar.classList.contains('collapsed') ? '»' : '«';
        });

        // Mobile menu toggle
        mobileMenuToggle.addEventListener('click', () => {
            sidebar.classList.toggle('collapsed');
        });

        // Toggle submenu
        function toggleSubmenu(e, element) {
            e.preventDefault();
            const submenu = element.nextElementSibling;
            if (submenu && submenu.classList.contains('submenu')) {
                submenu.classList.toggle('open');
            }
        }

        // Set active nav item on click
        document.querySelectorAll('.nav-item').forEach(item => {
            item.addEventListener('click', function(e) {
                if (!this.nextElementSibling || !this.nextElementSibling.classList.contains('submenu')) {
                    e.preventDefault();
                    document.querySelectorAll('.nav-item').forEach(i => i.classList.remove('active'));
                    this.classList.add('active');
                }
            });
        });
    </script>
</body>
</html>