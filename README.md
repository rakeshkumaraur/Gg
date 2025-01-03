<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Trend Sphare Coding - News, Blogs, and Coding Tutorials">
    <meta name="keywords" content="News, Blogs, Coding, Tutorials, Technology">
    <meta name="author" content="Trend Sphare Coding">
    <title>Trend Sphare Coding</title>
    <link rel="stylesheet" href="styles.css">
    <script defer src="scripts.js"></script>
</head>
<body>
    <header>
        <div class="logo">
            <h1>Trend Sphare Coding</h1>
        </div>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#news">News</a></li>
                <li><a href="#blogs">Blogs</a></li>
                <li><a href="#coding">Coding Tutorials</a></li>
                <li><a href="#auth">Login</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="home">
            <h2>Welcome to Trend Sphare Coding</h2>
            <p>Your one-stop destination for news, blogs, and coding insights!</p>
        </section>

        <section id="news">
            <h2>Latest News</h2>
            <div class="news-feed">
                <!-- Dynamic news content will be loaded here -->
            </div>
        </section>

        <section id="blogs">
            <h2>Blogs</h2>
            <p>Explore in-depth articles and opinions on various topics.</p>
        </section>

        <section id="coding">
            <h2>Coding Tutorials</h2>
            <p>Learn coding step-by-step with our tutorials.</p>
        </section>

        <section id="auth">
            <h2>Login to Your Account</h2>
            <form action="/login" method="POST">
                <label for="username">Username:</label>
                <input type="text" id="username" name="username" required>
                <label for="password">Password:</label>
                <input type="password" id="password" name="password" required>
                <button type="submit">Login</button>
            </form>
        </section>

        <section id="search">
            <h2>Search</h2>
            <input type="text" id="search-bar" placeholder="Search articles or tutorials...">
            <button onclick="searchContent()">Search</button>
        </section>

        <section id="subscribe">
            <h2>Subscribe to Our Newsletter</h2>
            <form action="/subscribe" method="POST">
                <input type="email" name="email" placeholder="Enter your email" required>
                <button type="submit">Subscribe</button>
            </form>
        </section>
    </main>

    <footer>
        <p>&copy; 2024 Trend Sphare Coding. All rights reserved.</p>
        <p>Follow us:
            <a href="https://twitter.com">Twitter</a> | 
            <a href="https://facebook.com">Facebook</a> | 
            <a href="https://linkedin.com">LinkedIn</a>
        </p>
    </footer>

    <script>
        // JavaScript functionality for dynamic news and search
        function searchContent() {
            const query = document.getElementById('search-bar').value.toLowerCase();
            alert('Search functionality coming soon! Query: ' + query);
        }

        document.addEventListener('DOMContentLoaded', () => {
            fetch('https://newsapi.org/v2/top-headlines?apiKey=YOUR_API_KEY')
                .then(response => response.json())
                .then(data => {
                    const newsFeed = document.querySelector('.news-feed');
                    data.articles.forEach(article => {
                        const newsItem = document.createElement('article');
                        newsItem.innerHTML = `
                            <h3>${article.title}</h3>
                            <p>${article.description}</p>
                            <a href="${article.url}" target="_blank">Read more</a>
                        `;
                        newsFeed.appendChild(newsItem);
                    });
                })
                .catch(error => console.error('Error fetching news:', error));
        });
    </script>
</body>
</html>
