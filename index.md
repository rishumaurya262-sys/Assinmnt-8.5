# Assignment 8.5 — CSS Grid Mini-Project

## Objective

Build a complete responsive photo-gallery website using CSS Grid. The project demonstrates responsive columns, named grid areas, consistent spacing, and overflow prevention.

## 1. HTML Code (`index.html`)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Explore Gallery</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="website-layout">

        <header class="header">
            <div class="logo">Explore Gallery</div>
            <nav class="navigation">
                <a href="#">Home</a>
                <a href="#gallery">Gallery</a>
                <a href="#about">About</a>
            </nav>
        </header>

        <main class="main-content">
            <section class="hero">
                <h1>Discover the Beauty of Nature</h1>
                <p>Explore beautiful landscapes, mountains, forests, and oceans.</p>
            </section>

            <section class="gallery-section" id="gallery">
                <h2>Featured Photos</h2>

                <div class="gallery-grid">
                    <article class="gallery-card">
                        <img src="https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?auto=format&fit=crop&w=800&q=80" alt="Beautiful natural landscape">
                        <div class="card-content">
                            <h3>Beautiful Landscape</h3>
                            <p>Enjoy the peaceful beauty of nature.</p>
                        </div>
                    </article>

                    <article class="gallery-card">
                        <img src="https://images.unsplash.com/photo-1470770841072-f978cf4d019e?auto=format&fit=crop&w=800&q=80" alt="Mountain lake">
                        <div class="card-content">
                            <h3>Mountain Lake</h3>
                            <p>A relaxing view surrounded by mountains.</p>
                        </div>
                    </article>

                    <article class="gallery-card">
                        <img src="https://images.unsplash.com/photo-1441974231531-c6227db76b6e?auto=format&fit=crop&w=800&q=80" alt="Green forest">
                        <div class="card-content">
                            <h3>Green Forest</h3>
                            <p>Discover the calm atmosphere of a forest.</p>
                        </div>
                    </article>

                    <article class="gallery-card">
                        <img src="https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?auto=format&fit=crop&w=800&q=80" alt="High mountain peaks">
                        <div class="card-content">
                            <h3>Mountain Peaks</h3>
                            <p>Magnificent mountains reaching the sky.</p>
                        </div>
                    </article>

                    <article class="gallery-card">
                        <img src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&w=800&q=80" alt="Sunny beach and ocean">
                        <div class="card-content">
                            <h3>Sunny Beach</h3>
                            <p>Relax beside the beautiful blue ocean.</p>
                        </div>
                    </article>

                    <article class="gallery-card">
                        <img src="https://images.unsplash.com/photo-1518837695005-2083093ee35b?auto=format&fit=crop&w=800&q=80" alt="Ocean waves">
                        <div class="card-content">
                            <h3>Ocean Waves</h3>
                            <p>Watch the waves move across the sea.</p>
                        </div>
                    </article>
                </div>
            </section>

            <section class="about" id="about">
                <h2>About This Gallery</h2>
                <p>This mini-project demonstrates how CSS Grid can create an organized, responsive photo-gallery website.</p>
            </section>
        </main>

        <footer class="footer">
            <p>&copy; 2026 Explore Gallery. All rights reserved.</p>
        </footer>

    </div>

</body>
</html>
```

## 2. CSS Code (`style.css`)

```css
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Arial, sans-serif;
    color: #1f2937;
    background-color: #f4f7fb;
    line-height: 1.6;
}

.website-layout {
    display: grid;
    grid-template-columns: minmax(0, 1fr);
    grid-template-areas:
        "header"
        "main"
        "footer";
    min-height: 100vh;
}

/* Header */
.header {
    grid-area: header;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 15px;
    padding: 18px 5%;
    color: white;
    background-color: #17365d;
}

.logo {
    font-size: 24px;
    font-weight: bold;
}

.navigation {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.navigation a {
    color: white;
    text-decoration: none;
}

.navigation a:hover {
    color: #ffd166;
}

/* Main content */
.main-content {
    grid-area: main;
    min-width: 0;
    width: 100%;
}

/* Hero section */
.hero {
    padding: 55px 20px;
    text-align: center;
    color: white;
    background-color: #28666e;
}

.hero h1 {
    margin-top: 0;
    font-size: clamp(26px, 4vw, 42px);
}

.hero p {
    max-width: 650px;
    margin: 0 auto;
}

/* Gallery section */
.gallery-section {
    max-width: 1200px;
    margin: 0 auto;
    padding: 35px 20px;
}

.gallery-section h2,
.about h2 {
    margin-top: 0;
    text-align: center;
}

/* Responsive CSS Grid */
.gallery-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(min(100%, 260px), 1fr));
    gap: 22px;
    align-items: stretch;
}

.gallery-card {
    min-width: 0;
    overflow: hidden;
    background-color: white;
    border-radius: 12px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
}

.gallery-card img {
    display: block;
    width: 100%;
    max-width: 100%;
    height: 220px;
    object-fit: cover;
}

.card-content {
    padding: 16px;
    overflow-wrap: anywhere;
}

.card-content h3 {
    margin: 0 0 8px;
    color: #17365d;
}

.card-content p {
    margin: 0;
    color: #555;
}

/* About section */
.about {
    max-width: 900px;
    margin: 0 auto;
    padding: 25px 20px 40px;
    text-align: center;
}

/* Footer */
.footer {
    grid-area: footer;
    padding: 20px;
    text-align: center;
    color: white;
    background-color: #17365d;
}

/* Mobile adjustments */
@media (max-width: 600px) {
    .header {
        justify-content: center;
        text-align: center;
        padding: 18px 12px;
    }

    .navigation {
        justify-content: center;
        gap: 14px;
    }

    .hero {
        padding: 35px 15px;
    }

    .gallery-section {
        padding: 25px 14px;
    }

    .gallery-grid {
        grid-template-columns: repeat(auto-fit, minmax(min(100%, 220px), 1fr));
        gap: 15px;
    }

    .gallery-card img {
        height: 200px;
    }
}
```

## 3. Requirements Completed

* Created a header and footer.
* Built a photo gallery with six image cards.
* Used CSS Grid for the primary layout.
* Used `repeat()`, `minmax()`, and `fr` units for responsive columns.
* Used named grid areas for the page layout.
* Applied consistent spacing with `gap`.
* Prevented image overflow using `width: 100%`, `max-width: 100%`, and `overflow: hidden`.
* Used `min-width: 0` and `overflow-wrap: anywhere` to help prevent text overflow.
* Added a mobile layout using a media query.

## 4. Testing

1. Open `index.html` in your browser.
2. Confirm that all six image cards appear.
3. View the page at desktop width.
4. Reduce the browser width and verify that the grid columns adjust automatically.
5. Check that images and text do not overflow their cards.
6. Test the layout on a mobile-sized screen.
7. Capture desktop and mobile screenshots.

## Result

A responsive photo-gallery website built with CSS Grid, featuring multiple cards, consistent spacing, named grid areas, and a responsive layout.

## Submission

* `Assignment-8.5.md`
* `index.html`
* `style.css`
* Desktop screenshot
* Mobile screenshot
* GitHub repository link
*