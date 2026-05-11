<!DOCTYPE html>
<html>
<head>
    <title>Library Management System</title>
    <style>
        /* Professional Blue Theme CSS Styles */
        :root {
            --primary-blue: #1e3a8a;
            --secondary-blue: #3b82f6;
            --light-blue: #eff6ff;
            --border-blue: #bfdbfe;
            --accent-blue: #60a5fa;
        }

        header {
            text-align: center;
            padding: 2em;
            background-color: var(--primary-blue);
            color: white;
            background-image: url('c.jpg'); /* Your original image */
            background-size: cover;
            background-blend-mode: overlay;
        }

        nav {
            padding: 1em 0;
            text-align: center;
            background-color: #f8fafc;
            border-bottom: 2px solid var(--border-blue);
        }

        nav ul {
            margin: 5px 0;
            padding: 0;
        }

        nav ul li {
            display: inline;
            margin: 0 1.5em;
        }

        nav ul li a {
            text-decoration: none;
            color: var(--primary-blue);
            font-weight: bold;
        }

        nav ul li a:hover {
            color: var(--secondary-blue);
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 1em;
        }

        th, td {
            border: 1px solid var(--border-blue);
            padding: 12px;
            text-align: left;
        }

        th {
            background-color: var(--primary-blue);
            color: white;
        }

        tr {
            background-color: white;
        }

        tr:nth-child(even) {
            background-color: var(--light-blue);
        }

        form label {
            display: block;
            margin-bottom: 0.5em;
            font-weight: 600;
            color: #334155;
        }

        form input, form select {
            padding: 8px;
            margin-bottom: 1em;
            border: 1px solid var(--border-blue);
            border-radius: 4px;
            width: 250px;
        }

        form button, button {
            background-color: var(--primary-blue);
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background 0.3s;
        }

        form button:hover, button:hover {
            background-color: var(--secondary-blue);
        }

        #results {
            margin-top: 1em;
            padding: 1em;
            border: 1px solid var(--accent-blue);
            background-color: var(--light-blue);
            border-radius: 4px;
        }

        #login-section {
            background-color: var(--light-blue);
            padding: 8em 2em;
            text-align: center;
        }

        #login-form {
            display: inline-block;
            text-align: left;
            background: white;
            padding: 2em;
            border-radius: 8px;
            box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1);
        }

        .section {
            padding: 2em;
            max-width: 1200px;
            margin: auto;
        }

        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <header>
        <h1>Library Management System</h1>
        <p><i>Manage and View Library Books</i></p>
    </header>

    <link rel="stylesheet" href="lsm.css">
    <nav class="hidden" id="main-nav">
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About Us</a></li>
        </ul>
        <ul>
            <li><a href="#view-books">View Books</a></li>
            <li><a href="#add-book">Add Book</a></li>
            <li><a href="#delete-book">Delete Book</a></li>
        </ul>
    </nav>

    <section id="login-section">
        <h2>User Login</h2>
        <form id="login-form">
            <label for="username">Username:</label>
            <input type="text" id="username" name="username" required>
            <label for="password">Password:</label>
            <input type="password" id="password" name="password" required>
            <div>
                <button type="submit">Login</button>
                <div id="login-message" style="color: #dc2626; margin-top: 10px;"></div>
            </div>
        </form>
    </section>

    <section id="home" class="section hidden">
        <h1><b>Welcome to the library</b></h1>
        <p><i>Welcome to our Library Management System! Here, you can efficiently manage our collection by adding new titles, removing existing ones, and quickly searching for specific books. Our intuitive interface also allows you to easily find details such as the author's name and the year of publication for every book in our library.</i></p>
    </section>

    <section id="about" class="section hidden">
        <h1><b>About Us</b></h1>
        <p><i>It typically contains 20 books, including fiction, non-fiction, reference books, biographies, historical texts, encyclopedias, magazines, and academic journals.</i></p>
    </section>

    <section id="view-books" class="section hidden">
        <h1>Library Book Locator</h1>
        <label for="bookTitle">Enter Book Title:</label>
        <input type="text" id="bookTitle" name="bookTitle">
        <button onclick="findBook()">Find Book</button>
        <div id="results"></div>
        <table id="books-table">
            <thead>
                <tr>
                    <th>Book Title</th>
                    <th>Author</th>
                    <th>Category</th>
                    <th>Year</th>
                    <th>Location</th>
                </tr>
            </thead>
            <tbody>
                <tr><td>Wings of Fire</td><td>A.P.J. Abdul Kalam</td><td>Non-fiction</td><td>1999</td><td>Rack 1, Shelf 1</td></tr>
                <tr><td>The Discovery of India</td><td>Jawaharlal Nehru</td><td>Non-fiction</td><td>1946</td><td>Rack 1, Shelf 2</td></tr>
                <tr><td>India Unbound</td><td>Gurcharan Das</td><td>Non-fiction</td><td>2000</td><td>Rack 1, Shelf 3</td></tr>
                <tr><td>Ignited Minds</td><td>A.P.J. Abdul Kalam</td><td>Non-fiction</td><td>2002</td><td>Rack 1, Shelf 4</td></tr>
                <tr><td>A Brief History of Modern India</td><td>Rajiv Ahir (Spectrum)</td><td>Non-fiction</td><td>2014</td><td>Rack 2, Shelf 1</td></tr>
                <tr><td>The Story of My Experiments with Truth</td><td>M.K. Gandhi</td><td>Autobiography</td><td>1927</td><td>Rack 2, Shelf 2</td></tr>
                <tr><td>Fun with Mathematics</td><td>Vikas Gupta</td><td>Non-fiction</td><td>2011</td><td>Rack 2, Shelf 3</td></tr>
                <tr><td>Grandfather's Private Zoo</td><td>Ruskin Bond</td><td>Fiction</td><td>1991</td><td>Rack 2, Shelf 4</td></tr>
                <tr><td>Number the Stars (Indian ed.)</td><td>Lois Lowry (translated)</td><td>Fiction</td><td>2005</td><td>Rack 3, Shelf 1</td></tr>
                <tr><td>The Blue Umbrella</td><td>Ruskin Bond</td><td>Fiction</td><td>1974</td><td>Rack 3, Shelf 2</td></tr>
                <tr><td>Gitanjali (Song Offerings)</td><td>Rabindranath Tagore</td><td>Poetry</td><td>1910</td><td>Rack 3, Shelf 3</td></tr>
                <tr><td>Mathematics for Class 10 (NCERT)</td><td>NCERT Authors</td><td>Non-fiction</td><td>Yearly</td><td>Rack 3, Shelf 4</td></tr>
                <tr><td>History of Medieval India</td><td>Satish Chandra</td><td>Non-fiction</td><td>2007</td><td>Rack 4, Shelf 1</td></tr>
                <tr><td>The Argumentative Indian</td><td>Amartya Sen</td><td>Non-fiction</td><td>2005</td><td>Rack 4, Shelf 2</td></tr>
                <tr><td>Manorama Yearbook</td><td>Malayala Manorama Group</td><td>Non-fiction</td><td>Annual</td><td>Rack 4, Shelf 3</td></tr>
                <tr><td>We the Children of India</td><td>Leila Seth</td><td>Non-fiction</td><td>2010</td><td>Rack 4, Shelf 4</td></tr>
                <tr><td>The Constitution of India for Children</td><td>Subhadra Sen Gupta</td><td>Non-fiction</td><td>2020</td><td>Rack 5, Shelf 1</td></tr>
                <tr><td>Panchtantra Stories</td><td>Vishnu Sharma (retold)</td><td>Fiction</td><td>Ancient (Retold)</td><td>Rack 5, Shelf 2</td></tr>
                <tr><td>Geography of India</td><td>Majid Husain</td><td>Non-fiction</td><td>2017</td><td>Rack 5, Shelf 3</td></tr>
                <tr><td>Exam Warriors</td><td>Narendra Modi</td><td>Non-fiction</td><td>2018</td><td>Rack 5, Shelf 4</td></tr>
            </tbody>
        </table>
    </section>

    <section id="add-book" class="section hidden">
        <h2>Add a New Book</h2>
        <form id="add-book-form">
            <label for="title">Book Title:</label>
            <input type="text" id="title" name="title" required>
            <label for="author">Author:</label>
            <input type="text" id="author" name="author" required>
            <label for="genre">Category:</label>
            <input type="text" id="genre" name="genre" required>
            <label for="year">Year:</label>
            <input type="number" id="year" name="year" required>
            <label for="location">Location:</label>
            <input type="text" id="location" name="location" required>
            <button type="submit">Add Book</button>
        </form>
    </section>

    <section id="delete-book" class="section hidden">
        <h2>Delete a Book</h2>
        <form id="delete-book-form">
            <label for="deleteTitle">Book Title to Delete:</label>
            <input type="text" id="deleteTitle" name="deleteTitle" required>
            <button type="submit">Delete Book</button>
        </form>
    </section>

    <script>
        // JavaScript Functionality (Preserved exactly as original)
        const validUsername = "student";
        const validPassword = "1234";

        const loginForm = document.getElementById('login-form');
        const loginSection = document.getElementById('login-section');
        const mainNav = document.getElementById('main-nav');
        const mainSections = document.querySelectorAll('.section:not(#login-section)');
        const loginMessage = document.getElementById('login-message');

        loginForm.addEventListener('submit', function(event) {
            event.preventDefault();
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;

            if (username === validUsername && password === validPassword) {
                loginSection.classList.add('hidden');
                mainNav.classList.remove('hidden');
                mainSections.forEach(section => section.classList.remove('hidden'));
            } else {
                loginMessage.textContent = "Invalid username or password.";
            }
        });

        function findBook() {
            const bookTitle = document.getElementById("bookTitle").value.toLowerCase();
            const resultsDiv = document.getElementById("results");
            const table = document.getElementById('books-table').getElementsByTagName('tbody')[0];
            const rows = table.getElementsByTagName('tr');
            let foundBook = null;

            for (let i = 0; i < rows.length; i++) {
                const cells = rows[i].getElementsByTagName('td');
                if (cells.length > 0) {
                    const currentTitle = cells[0].textContent.toLowerCase();
                    if (currentTitle === bookTitle) {
                        foundBook = {
                            title: cells[0].textContent,
                            author: cells[1].textContent,
                            genre: cells[2].textContent,
                            year: cells[3].textContent,
                            location: cells[4] ? cells[4].textContent : 'N/A',
                        };
                        break;
                    }
                }
            }

            if (foundBook) {
                resultsDiv.innerHTML = `<p><strong>${foundBook.title}</strong> is found.<br>
                Author: ${foundBook.author}, <br> Genre: ${foundBook.genre}, <br>
                Year: ${foundBook.year}, <br> Location: ${foundBook.location}</p>`;
            } else {
                resultsDiv.innerHTML = "<p>Book not found.</p>";
            }
        }

        document.getElementById('add-book-form').addEventListener('submit', function(event) {
            event.preventDefault();
            const title = document.getElementById('title').value;
            const author = document.getElementById('author').value;
            const genre = document.getElementById('genre').value;
            const year = document.getElementById('year').value;
            const location = document.getElementById('location').value;

            const table = document.getElementById('books-table').getElementsByTagName('tbody')[0];
            const newRow = table.insertRow(table.rows.length);
            newRow.innerHTML = `<td>${title}</td><td>${author}</td><td>${genre}</td><td>${year}</td><td>${location}</td>`;

            document.getElementById('title').value = '';
            document.getElementById('author').value = '';
            document.getElementById('genre').value = '';
            document.getElementById('year').value = '';
            document.getElementById('location').value = '';
        });

        document.getElementById('delete-book-form').addEventListener('submit', function(event) {
            event.preventDefault();
            const deleteTitle = document.getElementById('deleteTitle').value.toLowerCase();
            const table = document.getElementById('books-table').getElementsByTagName('tbody')[0];
            const rows = table.getElementsByTagName('tr');

            for (let i = 0; i < rows.length; i++) {
                const cells = rows[i].getElementsByTagName('td');
                if (cells.length > 0 && cells[0].textContent.toLowerCase() === deleteTitle) {
                    table.deleteRow(i);
                    break;
                }
            }
            document.getElementById('deleteTitle').value = '';
        });
    </script>
</body>
</html>
* { box-sizing: border-box; }

#add-book, #delete-book {
    /* Changed from #28EAFF (Cyan) to a soft professional light blue */
    background-color: #e0f2fe; 
    padding: 1em;
    border-radius: 10px;
    border: 1px solid #bae6fd;
}

nav ul {
    /* Changed from #A13F3F (Red) to a Deep Navy Blue */
    background-color: #1e3a8a;
    padding: 1em;
    list-style: none;
}

nav ul li a {
    color: white;
    font-size: 1.2em;
}

.section {
    padding: 40px 20px;
    margin: 20px 0;
    display: none;
}

section:target {
    display: block;
}

#home {
    /* Changed from #A13F6A (Magenta) to a clean Royal Blue */
    background-color: #2563eb;
    color: white;
}

#about {
    /* Changed from #A13F6A (Magenta) to a professional Slate Blue */
    background-color: #334155;
    color: white;
}
