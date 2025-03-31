# DropBox
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dropbox Clone - Help & Support</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        .accordion-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
        }
        .accordion.active .accordion-content {
            max-height: 500px;
        }
    </style>
</head>
<body class="bg-white text-gray-800">
    <!-- Header -->
    <div id="header"></div>

    <main>
        <!-- Help Hero Section -->
        <section class="bg-blue-50 py-16 px-4">
            <div class="max-w-6xl mx-auto text-center">
                <h1 class="text-3xl md:text-4xl font-bold mb-6">How can we help?</h1>
                <div class="max-w-2xl mx-auto relative">
                    <input type="text" placeholder="Search help articles..." class="w-full px-6 py-4 rounded-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-500">
                    <button class="absolute right-3 top-3 text-gray-400 hover:text-blue-600">
                        <i class="fas fa-search"></i>
                    </button>
                </div>
            </div>
        </section>

        <!-- FAQ Section -->
        <section class="py-16 px-4">
            <div class="max-w-4xl mx-auto">
                <h2 class="text-2xl font-bold mb-8">Frequently asked questions</h2>
                
                <!-- FAQ Item 1 -->
                <div class="accordion mb-4 border-b border-gray-200 pb-4">
                    <button class="accordion-btn w-full flex justify-between items-center text-left font-medium text-lg">
                        <span>How do I sign up for Dropbox?</span>
                        <i class="fas fa-chevron-down transition-transform"></i>
                    </button>
                    <div class="accordion-content mt-2 text-gray-600">
                        <p>To sign up for Dropbox, go to our homepage and click "Sign up free". You can create an account using your email address or sign up with Google. Follow the on-screen instructions to complete your registration.</p>
                    </div>
                </div>

                <!-- FAQ Item 2 -->
                <div class="accordion mb-4 border-b border-gray-200 pb-4">
                    <button class="accordion-btn w-full flex justify-between items-center text-left font-medium text-lg">
                        <span>How do I recover deleted files?</span>
                        <i class="fas fa-chevron-down transition-transform"></i>
                    </button>
                    <div class="accordion-content mt-2 text-gray-600">
                        <p>Deleted files can be recovered from the Dropbox website. Go to the "Deleted files" section in your account settings. Files are kept for 30 days in the Basic plan, 180 days in Plus, and 1 year in Professional.</p>
                    </div>
                </div>

                <!-- FAQ Item 3 -->
                <div class="accordion mb-4 border-b border-gray-200 pb-4">
                    <button class="accordion-btn w-full flex justify-between items-center text-left font-medium text-lg">
                        <span>How do I share files with others?</span>
                        <i class="fas fa-chevron-down transition-transform"></i>
                    </button>
                    <div class="accordion-content mt-2 text-gray-600">
                        <p>Right-click on any file or folder in your Dropbox and select "Share". You can enter email addresses or generate a shareable link. You can control whether recipients can view or edit the content.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="py-16 px-4 bg-gray-50">
            <div class="max-w-4xl mx-auto">
                <h2 class="text-2xl font-bold mb-8">Contact our support team</h2>
                <form class="space-y-6">
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <label for="name" class="block text-sm font-medium text-gray-700 mb-1">Name</label>
                            <input type="text" id="name" class="w-full px-4 py-2 rounded-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-500">
                        </div>
                        <div>
                            <label for="email" class="block text-sm font-medium text-gray-700 mb-1">Email</label>
                            <input type="email" id="email" class="w-full px-4 py-2 rounded-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-500">
                        </div>
                    </div>
                    <div>
                        <label for="subject" class="block text-sm font-medium text-gray-700 mb-1">Subject</label>
                        <input type="text" id="subject" class="w-full px-4 py-2 rounded-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-500">
                    </div>
                    <div>
                        <label for="message" class="block text-sm font-medium text-gray-700 mb-1">Message</label>
                        <textarea id="message" rows="4" class="w-full px-4 py-2 rounded-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-500"></textarea>
                    </div>
                    <button type="submit" class="bg-blue-600 hover:bg-blue-700 text-white font-medium px-6 py-3 rounded-lg transition-colors">Send Message</button>
                </form>
            </div>
        </section>

        <!-- Footer -->
        <div id="footer"></div>
    </main>

    <script>
        // Load header and footer components
        fetch('header.html')
            .then(response => response.text())
            .then(data => document.getElementById('header').innerHTML = data);
        
        fetch('footer.html')
            .then(response => response.text())
            .then(data => document.getElementById('footer').innerHTML = data);

        // Accordion functionality
        document.querySelectorAll('.accordion-btn').forEach(button => {
            button.addEventListener('click', () => {
                const accordion = button.closest('.accordion');
                const icon = button.querySelector('i');
                
                accordion.classList.toggle('active');
                icon.classList.toggle('rotate-180');
            });
        });  
    </script>
</body>
</html>    
