# Gift-Finder
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gift Ideas</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.1.1/css/all.min.css">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #ffcccc;
        }
        .landing-page {
        background-image: linear-gradient(to bottom, #ffe6e6, #ffffff);
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        }
        .gift-idea-generator {
            display: none;
        }
        .header {
            background-color: #ff69b4;
            color: #ffffff;
            padding: 20px;
            text-align: center;
        }
        .occasion-select {
            width: 200px;
            margin: 20px;
            border: 1px solid #ffcccc;
            border-radius: 10px;
            padding: 10px;
        }
        .tag-select {
            margin: 20px;
        }
        .gift-ideas-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }
        .gift-idea {
            background-color: #ffffff;
            padding: 20px;
            border: 1px solid #ffcccc;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .gift-idea img {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-radius: 10px 10px 0 0;
        }
        .gift-idea h5 {
            margin-top: 10px;
            color: #ff69b4;
        }
        .gift-idea p {
            font-size: 14px;
            color: #666;
        }
        .modal-content {
            background-color: #ffffff;
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .modal-header {
            border-bottom: 1px solid #ddd;
            background-color: #ff69b4;
            color: #ffffff;
        }
        .modal-body {
            padding: 20px;
        }
        .modal-footer {
            border-top: 1px solid #ddd;
        }
        .btn-primary {
            background-color: #ff69b4;
            border-color: #ff69b4;
        }
        .btn-primary:hover {
            background-color: #ff99cc;
            border-color: #ff99cc;
        }
        .hero {
            background-image: linear-gradient(to bottom, #ff99cc, #ffe6f2);
            padding: 200px 0;
            background-size: cover;
            background-position: center;
        }
        .featured-gifts {
            padding: 100px 0;
            background-color: #ffffff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .testimonial {
            padding: 100px 0;
            background-color: #f2f2f2;
        }
        .footer {
            padding: 50px 0;
            background-color: #333;
            color: #fff;
        }
        .gift-card {
            background-color: #f176b8;
            border: 1px solid #ddd;
            border-radius: 10px;
            padding: 20px;
            margin: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .gift-card:hover {
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
        }
        #welcome-hero {
            background-image: url('https://via.placeholder.com/1920x1080');
            background-size: cover;
            background-position: center;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            color: #11abed;
        }
        .header {
            background-color: #f599c7;
            color: #ffffff;
            padding: 20px;
            text-align: center;
        }
        .occasion-select {
            width: 200px;
            margin: 20px;
            border: 1px solid #ffcccc;
            border-radius: 10px;
            padding: 10px;
        }
        .tag-select {
            margin: 20px;
        }
        .gift-ideas-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }
        .gift-idea {
            background-color: #ffffff;
            padding: 20px;
            border: 1px solid #ffcccc;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .gift-idea img {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-radius: 10px 10px 0 0;
        }
        .gift-idea h5 {
            margin-top: 10px;
            color: #ff69b4;
        }
        .gift-idea p {
            font-size: 14px;
            color: #666;
        }
        .modal-content {
            background-color: #ffffff;
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .modal-header {
            border-bottom: 1px solid #ddd;
            background-color: #ff69b4;
            color: #ffffff;
        }
        .modal-body {
            padding: 20px;
        }
        .modal-footer {
            border-top: 1px solid #ddd;
        }
        .btn-primary {
            background-color: #ff69b4;
            border-color: #ff69b4;
        }
        .btn-primary:hover {
            background-color: #ff99cc;
            border-color: #ff99cc;
        }
        .footer {
            background-color: #333;
            color: #ffffff;
            padding: 20px;
            text-align: center;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <div class="landing-page">
        <h1 class="display-1">Gift Idea Generator</h1>
        <button class="btn btn-primary btn-lg" id="start-button">Get Started</button>
    </div>
    <div class="gift-idea-generator">
        <div class="header">
            <h1>Gift Idea Generator</h1>
        </div>
        <div class="container mt-5">
            <div class="row">
                <div class="col-md-6">
                    <select class="form-select occasion-select" id="occasion-select">
                        <option value="">Select an occasion</option>
                        <option value="birthday">Birthday</option>
                        <option value="anniversary">Anniversary</option>
                        <option value="holiday">Holiday</option>
                        <option value="wedding">Wedding</option>
                        <option value="graduation">Graduation</option>
                    </select>
                </div>
                <div class="col-md-6">
                    <div class="tag-select">
                        <input type="checkbox" id="romantic" value="romantic">
                        <label for="romantic">Romantic</label>
                        <input type="checkbox" id="funny" value="funny">
                        <label for="funny">Funny</label>
                        <input type="checkbox" id="luxury" value="luxury">
                        <label for="luxury">Luxury</label>
                        <input type="checkbox" id="personalized" value="personalized">
                        <label for="personalized">Personalized</label>
                    </div>
                </div>
            </div>
            <div class="row">
                <div class="col-md-12">
                    <input type="search" class="form-control" id="search-input" placeholder="Search gift ideas">
                </div>
            </div>
            <div class="gift-ideas-grid" id="gift-ideas-grid">
                <!-- Gift ideas will be generated here -->
            </div>
        </div>
         <!-- Modal for product details -->
         <div class="modal fade" id="product-details-modal" tabindex="-1" aria-hidden="true">
            <div class="modal-dialog modal-dialog-centered">
                <div class="modal-content">
                    <div class="modal-header">
                        <h5 class="modal-title" id="product-title"></h5>
                        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                    </div>
                    <div class="modal-body">
                        <img id="product-image" width="100%" height="200">
                        <p id="product-description"></p>
                        <p id="product-price"></p>
                    </div>
                    <div class="modal-footer">
                        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <nav class="navbar navbar-expand-lg navbar-light bg-light fixed-top">
        <div class="container">
            <a class="navbar-brand" href="#">Gift Ideas</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
                    <li class="nav-item"><a class="nav-link" href="#welcome-hero">Home</a></li>
                    <li class="nav-item"><a class="nav-link" href="#featured-gifts">Gift Ideas</a></li>
                    <li class="nav-item"><a class="nav-link" href="#testimonial">Testimonials</a></li>
                </ul>
            </div>
        </div>
    </nav>
    <div class="hero" id="hero" style="display: none;">
        <div class="container">
            <h1 class="display-3">Find the Perfect Gift</h1>
            <p class="lead">Discover unique gift ideas for any occasion</p>
            <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#birthdayModal">Birthday Gift Ideas</button>
            <button type="button" class="btn btn-success" data-bs-toggle="modal" data-bs-target="#weddingModal">Wedding Gift Ideas</button>
            <button type="button" class="btn btn-info" data-bs-toggle="modal" data-bs-target="#anniversaryModal">Anniversary Gift Ideas</button>
            <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#holidayModal">Holiday Gift Ideas</button>
            <button type="button" class="btn btn-danger" data-bs-toggle="modal" data-bs-target="#graduationModal">Graduation Gift Ideas</button>
            <button type="button" class="btn btn-secondary" data-bs-toggle="modal" data-bs-target="#newBabyModal">New Baby Gift Ideas</button>
        </div>
    </div>

    <div class="featured-gifts" id="featured-gifts">
        <div class="container">
            <h2 class="mb-4">Featured Gift Ideas</h2>
            <div class="row">
                <div class="col-md-4">
                    <div class="card gift-card" style="background-color: #ffe6f2;">
                        <img src="https://via.placeholder.com/200x150" class="card-img-top" alt="...">
                        <div class="card-body">
                            <h5 class="card-title" style="color: #ff99cc;">Personalized Photo Frame</h5>
                            <p class="card-text" style="color: #666;">A beautifully crafted photo frame with your loved one's name</p>
                        </div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="card gift-card" style="background-color: #ccffcc;">
                        <img src="https://via.placeholder.com/200x150" class="card-img-top" alt="...">
                        <div class="card-body">
                            <h5 class="card-title" style="color: #33cc33;">Customized Jewelry</h5>
                            <p class="card-text" style="color: #666;">A unique piece of jewelry with your special message</p>
                        </div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="card gift-card" style="background-color: #ffffcc;">
                        <img src="https://via.placeholder.com/200x150" class="card-img-top" alt="...">
                        <div class="card-body">
                            <h5 class="card-title" style="color: #ffff00;">Gourmet Food Basket</h5>
                            <p class="card-text" style="color: #666;">A delicious selection of gourmet foods and treats</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="testimonial" id="testimonial">
        <div class="container">
            <h2 class="mb-4">What Our Customers Say</h2>
            <div class="row">
                <div class="col-md-4">
                    <div class="card" style="background-color: #f2f2f2;">
                        <div class="card-body">
                            <p class="card-text" style="color: #666;">"I was so impressed with the gift ideas on this website! I found the perfect present for my sister's birthday."</p>
                            <h5 class="card-title" style="color: #ff99cc;">Emily R.</h5>
                        </div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="card" style="background-color: #f2f2f2;">
                        <div class="card-body">
                            <p class="card-text" style="color: #666;">"I love the variety of gift ideas on this website. I've found something for every occasion!"</p>
                            <h5 class="card-title" style="color: #33cc33;">David K.</h5>
                        </div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="card" style="background-color: #f2f2f2;">
                        <div class="card-body">
                            <p class="card-text" style="color: #666;">"This website has been a lifesaver for me. I've found so many great gift ideas for my friends and family!"</p>
                            <h5 class="card-title" style="color: #ffff00;">Sarah T.</h5>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="footer">
        <div class="container">
            <div class="row">
                <div class="col-md-4">
                    <h5 class="mb-3" style="color: #ffffff;">Contact Us</h5>
                    <p style="color: #ffffff;">Phone: 555-555-5555</p>
                    <p style="color: #ffffff;">Email: <a href="mailto:info@example.com" style="color: #ffffff;">info@example.com</a></p>
                </div>
                <div class="col-md-4">
                    <h5 class="mb-3" style="color: #ffffff;">Follow Us</h5>
                    <p style="color: #ffffff;"><i class="fa-brands fa-facebook" style="color: #3b5998;"></i> Facebook</p>
                    <p style="color: #ffffff;"><i class="fa-brands fa-twitter" style="color: #1da1f2;"></i> Twitter</p>
                    <p style="color: #ffffff;"><i class="fa-brands fa-instagram" style="color: #e1306c;"></i> Instagram</p>
                </div>
                <div class="col-md-4">
                    <h5 class="mb-3" style="color: #ffffff;">Newsletter</h5>
                    <p style="color: #ffffff;">Sign up for our newsletter to receive exclusive promotions and gift ideas!</p>
                </div>
            </div>
        </div>
    </div>

    <div class="modal fade" id="birthdayModal" tabindex="-1" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered modal-lg">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" style="color: #ff99cc;">Birthday Gift Ideas</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body" style="background-color: #ffe6f2;">
                    <ul id="birthday-ideas-list" style="list-style: none; padding: 0; margin: 0;">
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <div class="modal fade" id="weddingModal" tabindex="-1" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered modal-lg">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" style="color: #33cc33;">Wedding Gift Ideas</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body" style="background-color: #ccffcc;">
                    <ul id="wedding-ideas-list" style="list-style: none; padding: 0; margin: 0;">
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <div class="modal fade" id="anniversaryModal" tabindex="-1" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered modal-lg">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" style="color: #6666cc;">Anniversary Gift Ideas</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body" style="background-color: #ccccff;">
                    <ul id="anniversary-ideas-list" style="list-style: none; padding: 0; margin: 0;">
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <div class="modal fade" id="holidayModal" tabindex="-1" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered modal-lg">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" style="color: #ff9900;">Holiday Gift Ideas</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body" style="background-color: #ffffcc;">
                    <ul id="holiday-ideas-list" style="list-style: none; padding: 0; margin: 0;">
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <div class="modal fade" id="graduationModal" tabindex="-1" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered modal-lg">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" style="color: #0066cc;">Graduation Gift Ideas</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body" style="background-color: #add8e6;">
                    <ul id="graduation-ideas-list" style="list-style: none; padding: 0; margin: 0;">
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <div class="modal fade" id="newBabyModal" tabindex="-1" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered modal-lg">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" style="color: #cc99ff;">New Baby Gift Ideas</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body" style="background-color: #ffe6ff;">
                    <ul id="new-baby-ideas-list" style="list-style: none; padding: 0; margin: 0;">
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
    <script>
        const birthdayIdeas = [
            "Personalized photo album",
            "Concert tickets",
            "Luxury watch"
        ];

        const weddingIdeas = [
            "Customized cutting board",
            "Kitchen appliance",
            "Honeymoon package"
        ];

        const anniversaryIdeas = [
            "Weekend getaway",
            "Wine and cheese basket",
            "Diamond necklace"
        ];

        const holidayIdeas = [
            "Decorative ornament",
            "Gourmet cheese board",
            "Gift card to favorite store"
        ];

        const graduationIdeas = [
            "Laptop",
            "Career development book",
            "Personalized luggage"
        ];

        const newBabyIdeas = [
            "Baby blanket",
            "Toy set",
            "Nursery decor"
        ];
        // Gift ideas data
        const giftIdeas = [
            {
                id: 1,
                occasion: 'birthday',
                tags: ['romantic', 'funny'],
                title: 'Birthday Cake',
                description: 'A delicious birthday cake with candles',
                price: 20.99,
                image: 'https://source.unsplash.com/200x300/?birthday,cake'
            },
            {
                id: 2,
                occasion: 'anniversary',
                tags: ['romantic', 'luxury'],
                title: 'Anniversary Gift',
                description: 'A luxurious anniversary gift with a personal touch',
                price: 50.99,
                image: 'https://source.unsplash.com/200x300/?anniversary,gift'
            },
            {
                id: 3,
                occasion: 'holiday',
                tags: ['funny', 'luxury'],
                title: 'Holiday Gift',
                description: 'A funny and luxurious holiday gift for friends and family',
                price: 30.99,
                image: 'https://source.unsplash.com/200x300/?holiday,gift'
            },
            {
                id: 4,
                occasion: 'birthday',
                tags: ['funny'],
                title: 'Funny Birthday Mug',
                description: 'A funny birthday mug for the coffee lover',
                price: 15.99,
                image: 'https://source.unsplash.com/200x300/?funny,mug'
            },
            {
                id: 5,
                occasion: 'anniversary',
                tags: ['romantic'],
                title: 'Romantic Anniversary Dinner',
                description: 'A romantic anniversary dinner for two',
                price: 100.99,
                image: 'https://source.unsplash.com/200x300/?romantic,dinner'
            },
            {
                id: 6,
                occasion: 'wedding',
                tags: ['luxury', 'personalized'],
                title: 'Wedding Gift',
                description: 'A luxurious and personalized wedding gift for the happy couple',
                price: 200.99,
                image: 'https://source.unsplash.com/200x300/?wedding,gift'
            },
            {
                id: 7,
                occasion: 'graduation',
                tags: ['funny', 'personalized'],
                title: 'Graduation Gift',
                description: 'A funny and personalized graduation gift for the graduate',
                price: 25.99,
                image: 'https://source.unsplash.com/200x300/?graduation,gift'
            }
        ];

        // Function to generate gift ideas
        function generateGiftIdeas(occasion, tags, search) {
            const giftIdeasGrid = document.getElementById('gift-ideas-grid');
            giftIdeasGrid.innerHTML = '';

            giftIdeas.forEach(giftIdea => {
                if ((giftIdea.occasion === occasion || occasion === '') && (tags.length === 0 || giftIdea.tags.some(tag => tags.includes(tag))) && (search === '' || giftIdea.title.toLowerCase().includes(search.toLowerCase()) || giftIdea.description.toLowerCase().includes(search.toLowerCase()))) {
                    const giftIdeaHTML = `
                        <div class="gift-idea">
                            <img src="${giftIdea.image}" alt="${giftIdea.title}">
                            <h5>${giftIdea.title}</h5>
                            <p>$${giftIdea.price}</p>
                            <button class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#product-details-modal" onclick="showProductDetails(${giftIdea.id})">View Details</button>
                        </div>
                    `;
                    giftIdeasGrid.insertAdjacentHTML('beforeend', giftIdeaHTML);
                }
            });
        }

        // Function to show product details
        function showProductDetails(id) {
            const product = giftIdeas.find(giftIdea => giftIdea.id === id);
            document.getElementById('product-title').textContent = product.title;
            document.getElementById('product-image').src = product.image;
            document.getElementById('product-description').textContent = product.description;
            document.getElementById('product-price').textContent = `Price: $${product.price}`;
        }

        // Event listener for occasion select
        document.getElementById('occasion-select').addEventListener('change', event => {
            const occasion = event.target.value;
            const tags = Array.from(document.querySelectorAll('.tag-select input[type="checkbox"]:checked')).map(checkbox => checkbox.value);
            const search = document.getElementById('search-input').value;
            generateGiftIdeas(occasion, tags, search);
        });

        // Event listener for tag select
        document.querySelectorAll('.tag-select input[type="checkbox"]').forEach(checkbox => {
            checkbox.addEventListener('change', event => {
                const occasion = document.getElementById('occasion-select').value;
                const tags = Array.from(document.querySelectorAll('.tag-select input[type="checkbox"]:checked')).map(checkbox => checkbox.value);
                const search = document.getElementById('search-input').value;
                generateGiftIdeas(occasion, tags, search);
            });
        });

        // Event listener for search input
        document.getElementById('search-input').addEventListener('input', event => {
            const occasion = document.getElementById('occasion-select').value;
            const tags = Array.from(document.querySelectorAll('.tag-select input[type="checkbox"]:checked')).map(checkbox => checkbox.value);
            const search = event.target.value;
            generateGiftIdeas(occasion, tags, search);
        });

        // Event listener for start button
        document.getElementById('start-button').addEventListener('click', event => {
            document.querySelector('.landing-page').style.display = 'none';
            document.querySelector('.gift-idea-generator').style.display = 'block';
        });

        function generateBirthdayIdeas() {
            const birthdayIdeasList = document.getElementById("birthday-ideas-list");
            birthdayIdeas.forEach((idea) => {
                const listItem = document.createElement("LI");
                listItem.textContent = idea;
                listItem.style.color = "#666";
                birthdayIdeasList.appendChild(listItem);
            });
        }

        function generateWeddingIdeas() {
            const weddingIdeasList = document.getElementById("wedding-ideas-list");
            weddingIdeas.forEach((idea) => {
                const listItem = document.createElement("LI");
                listItem.textContent = idea;
                listItem.style.color = "#666";
                weddingIdeasList.appendChild(listItem);
            });
        }

        function generateAnniversaryIdeas() {
            const anniversaryIdeasList = document.getElementById("anniversary-ideas-list");
            anniversaryIdeas.forEach((idea) => {
                const listItem = document.createElement("LI");
                listItem.textContent = idea;
                listItem.style.color = "#666";
                anniversaryIdeasList.appendChild(listItem);
            });
        }

        function generateHolidayIdeas() {
            const holidayIdeasList = document.getElementById("holiday-ideas-list");
            holidayIdeas.forEach((idea) => {
                const listItem = document.createElement("LI");
                listItem.textContent = idea;
                listItem.style.color = "#666";
                holidayIdeasList.appendChild(listItem);
            });
        }

        function generateGraduationIdeas() {
            const graduationIdeasList = document.getElementById("graduation-ideas-list");
        };
    </script>
</body>
</html>
