
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flowerss Parfum - Wangi Bikin Menarik</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Chewy&family=Fredoka:wght@300;400;600&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    
    <!-- QR Code Generator Library -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'primary-pink': '#FF9EB5',
                        'soft-pink': '#FFE5EC',
                        'vivid-purple': '#D4A5FF',
                        'accent-yellow': '#FFF59D'
                    },
                    fontFamily: {
                        'body': ['Poppins', 'sans-serif'],
                        'heading': ['Fredoka', 'sans-serif'],
                        'cute': ['Chewy', 'cursive'],
                    }
                }
            }
        }
    </script>

    <style>
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #ffc3a0 0%, #ffafbd 100%);
            overflow-x: hidden;
        }

        /* Animasi Bunga Jatuh */
        .flower-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
            overflow: hidden;
        }

        .flower {
            position: absolute;
            top: -10%;
            animation: fall linear infinite;
            font-size: 24px;
        }

        @keyframes fall {
            0% { top: -10%; transform: translateX(0) rotate(0deg); opacity: 0.8; }
            100% { top: 110%; transform: translateX(100px) rotate(360deg); opacity: 0; }
        }

        /* Glassmorphism Cards */
        .glass-card {
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.5);
            border-radius: 20px;
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.15);
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(255, 105, 180, 0.3);
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }
        ::-webkit-scrollbar-track {
            background: #FFE5EC;
        }
        ::-webkit-scrollbar-thumb {
            background: #FF9EB5;
            border-radius: 5px;
        }
        
        /* Floating Cart Animation */
        @keyframes bounce-slow {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-5px); }
        }
        .cart-icon-anim {
            animation: bounce-slow 2s infinite;
        }
    </style>
</head>
<body class="text-gray-700 relative">

    <!-- Container untuk animasi bunga -->
    <div id="flower-container" class="flower-container"></div>

    <!-- Navigation -->
    <nav class="fixed w-full z-50 transition-all duration-300 bg-white/80 backdrop-blur-md shadow-sm" id="navbar">
        <div class="container mx-auto px-4 py-3 flex justify-between items-center">
            <a href="#" class="text-2xl font-heading font-bold text-pink-500 flex items-center gap-2">
                <i class="fas fa-spray-can text-vivid-purple"></i> Flowerss Parfum
            </a>
            
            <!-- Mobile Menu Button -->
            <button id="mobile-menu-btn" class="md:hidden text-pink-500 text-2xl">
                <i class="fas fa-bars"></i>
            </button>

            <!-- Desktop Menu -->
            <div class="hidden md:flex items-center gap-8 font-heading text-lg">
                <a href="#home" class="hover:text-pink-600 transition">Beranda</a>
                <a href="#about" class="hover:text-pink-600 transition">Tentang Kami</a>
                <a href="#products" class="hover:text-pink-600 transition">Produk</a>
                <a href="#testi" class="hover:text-pink-600 transition">Testimoni</a>
                <button onclick="toggleCart()" class="relative bg-gradient-to-r from-pink-400 to-purple-400 text-white px-5 py-2 rounded-full hover:shadow-lg transition transform hover:scale-105 cart-icon-anim">
                    <i class="fas fa-shopping-cart mr-2"></i> Keranjang
                    <span id="cart-count" class="absolute -top-2 -right-2 bg-red-500 text-white text-xs font-bold w-6 h-6 rounded-full flex items-center justify-center border-2 border-white">0</span>
                </button>
            </div>
        </div>
        
        <!-- Mobile Menu (Hidden by default) -->
        <div id="mobile-menu" class="hidden md:hidden bg-white/95 px-4 py-4 shadow-lg absolute w-full">
            <a href="#home" class="block py-2 text-pink-600 font-bold" onclick="toggleMobileMenu()">Beranda</a>
            <a href="#about" class="block py-2 text-pink-600" onclick="toggleMobileMenu()">Tentang Kami</a>
            <a href="#products" class="block py-2 text-pink-600" onclick="toggleMobileMenu()">Produk</a>
            <a href="#testi" class="block py-2 text-pink-600" onclick="toggleMobileMenu()">Testimoni</a>
            <button onclick="toggleCart(); toggleMobileMenu()" class="mt-2 w-full bg-pink-400 text-white py-2 rounded-lg">
                Keranjang
            </button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="relative pt-32 pb-20 px-4 min-h-screen flex items-center justify-center text-center">
        <div class="glass-card p-8 md:p-12 max-w-4xl w-full relative z-10 border-4 border-white/40">
            <span class="inline-block bg-pink-100 text-pink-600 px-4 py-1 rounded-full text-sm font-bold mb-4 tracking-wider animate-pulse">✨ BEST SELLER PERFUME</span>
            <h1 class="text-4xl md:text-6xl font-heading font-bold text-gray-800 mb-4 leading-tight">
                Wangi kan badan mu dengan <span class="text-transparent bg-clip-text bg-gradient-to-r from-pink-500 to-purple-500">Parfum Roll</span>
            </h1>
            <p class="text-xl md:text-2xl font-cute text-pink-500 mb-8 transform -rotate-2">
                "Parfum roll dengan wangi bikin menarik!!"
            </p>
            <p class="text-gray-600 mb-8 max-w-xl mx-auto">
                Praktis, hemat, dan tahan lama. Bawa keharuman bunga kemanapun kamu pergi dengan koleksi eksklusif kami.
            </p>
            <div class="flex flex-col md:flex-row gap-4 justify-center">
                <a href="#products" class="bg-gradient-to-r from-pink-500 to-purple-500 text-white px-8 py-3 rounded-full font-bold shadow-lg hover:shadow-pink-500/50 transition transform hover:-translate-y-1">
                    <i class="fas fa-shopping-bag mr-2"></i> Belanja Sekarang
                </a>
                <a href="#about" class="bg-white text-pink-500 border-2 border-pink-500 px-8 py-3 rounded-full font-bold hover:bg-pink-50 transition">
                    Kenalan Dulu
                </a>
            </div>
        </div>
    </section>

    <!-- About Us -->
    <section id="about" class="py-20 bg-white/50 backdrop-blur-sm">
        <div class="container mx-auto px-4">
            <div class="flex flex-col md:flex-row items-center gap-10">
                <div class="w-full md:w-1/2">
                    <div class="relative">
                        <!-- Placeholder Image for About -->
                        <div class="w-full h-80 bg-pink-200 rounded-3xl overflow-hidden shadow-xl flex items-center justify-center relative">
                            <i class="fas fa-heart text-9xl text-white opacity-50 absolute"></i>
                            <img src="https://images.unsplash.com/photo-1594035910387-fea47794261f?auto=format&fit=crop&q=80&w=800" alt="Parfum Aesthetic" class="object-cover w-full h-full opacity-90 hover:scale-110 transition duration-700">
                        </div>
                        <div class="absolute -bottom-5 -right-5 bg-yellow-200 p-4 rounded-full shadow-lg font-cute text-xl transform rotate-12">
                            🌸 100% Wangi!
                        </div>
                    </div>
                </div>
                <div class="w-full md:w-1/2">
                    <h2 class="text-3xl font-heading font-bold text-gray-800 mb-4">Tentang <span class="text-pink-500">Flowerss Parfum</span></h2>
                    <p class="text-gray-600 mb-4 leading-relaxed">
                        Kami percaya bahwa wangi adalah kunci kepercayaan diri. Flowerss Parfum hadir dengan kemasan Roll On yang praktis, mudah dibawa di saku atau tas kecilmu.
                    </p>
                    <p class="text-gray-600 mb-6 leading-relaxed">
                        Dibuat dengan bibit parfum pilihan yang menghasilkan aroma lembut, manis, dan menyegarkan tanpa membuat pusing. Cocok untuk sekolah, kuliah, atau hangout!
                    </p>
                    <ul class="space-y-2 font-medium text-gray-700">
                        <li class="flex items-center"><i class="fas fa-check-circle text-green-500 mr-2"></i> Non-Alkohol (Aman di kulit)</li>
                        <li class="flex items-center"><i class="fas fa-check-circle text-green-500 mr-2"></i> Tahan Lama seharian</li>
                        <li class="flex items-center"><i class="fas fa-check-circle text-green-500 mr-2"></i> Harga kantong pelajar</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products" class="py-20 px-4">
        <div class="container mx-auto">
            <div class="text-center mb-12">
                <span class="text-pink-600 font-bold tracking-widest uppercase text-sm">Pilihan Favorit</span>
                <h2 class="text-4xl font-heading font-bold text-gray-800 mt-2">Koleksi Wangi Kami</h2>
                <div class="w-24 h-1 bg-pink-500 mx-auto mt-4 rounded-full"></div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- Product 1 -->
                <div class="glass-card product-card p-6 flex flex-col items-center text-center transition-all duration-300">
                    <div class="w-48 h-48 bg-purple-100 rounded-full mb-6 flex items-center justify-center overflow-hidden shadow-inner relative group">
                        <div class="absolute inset-0 bg-black/10 hidden group-hover:flex items-center justify-center transition">
                            <span class="text-white font-bold">Lihat Detail</span>
                        </div>
                        <!-- Placeholder Image -->
                        <img src="https://images.unsplash.com/photo-1622618991746-fe6004db3a47?auto=format&fit=crop&q=80&w=400" class="object-cover w-full h-full" alt="Nagita Roll">
                    </div>
                    <h3 class="text-2xl font-heading font-bold text-gray-800">Nagita Roll</h3>
                    <p class="text-sm text-gray-500 mt-2 italic">"Elegan, mewah, dan berkelas seperti sultan."</p>
                    <div class="my-4 text-3xl font-cute text-pink-600">Rp 7.000</div>
                    <button onclick="addToCart(1, 'Nagita Roll', 7000)" class="w-full bg-pink-500 text-white py-3 rounded-xl font-bold hover:bg-pink-600 transition flex items-center justify-center gap-2">
                        <i class="fas fa-cart-plus"></i> Pesan Sekarang
                    </button>
                </div>

                <!-- Product 2 -->
                <div class="glass-card product-card p-6 flex flex-col items-center text-center transition-all duration-300 transform md:-translate-y-4 border-purple-300 border-2">
                    <div class="absolute top-4 right-4 bg-red-500 text-white text-xs font-bold px-3 py-1 rounded-full animate-bounce">POPULAR</div>
                    <div class="w-48 h-48 bg-pink-100 rounded-full mb-6 flex items-center justify-center overflow-hidden shadow-inner relative group">
                         <img src="https://images.unsplash.com/photo-1592945403244-b3fbafd7f539?auto=format&fit=crop&q=80&w=400" class="object-cover w-full h-full" alt="Sweet Boo Roll">
                    </div>
                    <h3 class="text-2xl font-heading font-bold text-gray-800">Sweet Boo Roll</h3>
                    <p class="text-sm text-gray-500 mt-2 italic">"Manis buah segar yang bikin ceria seharian."</p>
                    <div class="my-4 text-3xl font-cute text-pink-600">Rp 7.500</div>
                    <button onclick="addToCart(2, 'Sweet Boo Roll', 7500)" class="w-full bg-purple-500 text-white py-3 rounded-xl font-bold hover:bg-purple-600 transition flex items-center justify-center gap-2">
                        <i class="fas fa-cart-plus"></i> Pesan Sekarang
                    </button>
                </div>

                <!-- Product 3 -->
                <div class="glass-card product-card p-6 flex flex-col items-center text-center transition-all duration-300">
                    <div class="w-48 h-48 bg-yellow-100 rounded-full mb-6 flex items-center justify-center overflow-hidden shadow-inner relative group">
                        <img src="https://images.unsplash.com/photo-1616949755610-8c9ad0e42815?auto=format&fit=crop&q=80&w=400" class="object-cover w-full h-full" alt="Vanilla Cake Roll">
                    </div>
                    <h3 class="text-2xl font-heading font-bold text-gray-800">Vanilla Cake Roll</h3>
                    <p class="text-sm text-gray-500 mt-2 italic">"Lembut creamy seperti kue baru dipanggang."</p>
                    <div class="my-4 text-3xl font-cute text-pink-600">Rp 8.000</div>
                    <button onclick="addToCart(3, 'Vanilla Cake Roll', 8000)" class="w-full bg-pink-500 text-white py-3 rounded-xl font-bold hover:bg-pink-600 transition flex items-center justify-center gap-2">
                        <i class="fas fa-cart-plus"></i> Pesan Sekarang
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials -->
    <section id="testi" class="py-16 bg-white/40">
        <div class="container mx-auto px-4">
            <h2 class="text-3xl font-heading font-bold text-center text-gray-800 mb-10">Kata Mereka <i class="fas fa-comment-dots text-pink-500"></i></h2>
            <div class="flex flex-wrap justify-center gap-6">
                <!-- Testi 1 -->
                <div class="bg-white p-6 rounded-2xl shadow-md max-w-sm w-full border-l-4 border-pink-400">
                    <div class="flex text-yellow-400 mb-2">
                        <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
                    </div>
                    <p class="text-gray-600 italic mb-4">"Suka banget sama Sweet Boo! Wanginya nggak nyengat tapi awet banget dipake sekolah."</p>
                    <div class="font-bold text-gray-800">- Kak Rina, Pelajar</div>
                </div>
                <!-- Testi 2 -->
                <div class="bg-white p-6 rounded-2xl shadow-md max-w-sm w-full border-l-4 border-purple-400">
                    <div class="flex text-yellow-400 mb-2">
                        <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star-half-alt"></i>
                    </div>
                    <p class="text-gray-600 italic mb-4">"Vanilla Cake-nya beneran kayak kue! Cowokku sampe bilang wangi banget hehe."</p>
                    <div class="font-bold text-gray-800">- Kak Dinda, Mahasiswi</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Cart Modal (Hidden Overlay) -->
    <div id="cart-modal" class="fixed inset-0 z-[60] hidden">
        <!-- Backdrop -->
        <div class="absolute inset-0 bg-black/50 backdrop-blur-sm" onclick="toggleCart()"></div>
        
        <!-- Cart Content -->
        <div class="absolute right-0 top-0 h-full w-full md:w-[450px] bg-white shadow-2xl flex flex-col transition-transform transform translate-x-full" id="cart-panel">
            <div class="p-6 bg-pink-500 text-white flex justify-between items-center shadow-md">
                <h2 class="text-2xl font-heading font-bold"><i class="fas fa-shopping-basket"></i> Keranjang Kamu</h2>
                <button onclick="toggleCart()" class="text-white hover:text-gray-200 transition text-xl">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <!-- Items Area -->
            <div class="flex-1 overflow-y-auto p-6" id="cart-items">
                <!-- Cart items will be injected here via JS -->
                <div class="text-center text-gray-400 mt-10">
                    <i class="fas fa-cookie-bite text-6xl mb-4 opacity-50"></i>
                    <p>Keranjang masih kosong nih, yuk jajan parfum!</p>
                </div>
            </div>

            <!-- Total & Form -->
            <div class="p-6 bg-gray-50 border-t border-gray-200">
                <div class="flex justify-between items-center mb-6">
                    <span class="text-lg font-bold text-gray-600">Total Belanja:</span>
                    <span id="cart-total" class="text-2xl font-bold text-pink-600">Rp 0</span>
                </div>

                <!-- Checkout Form -->
                <form id="checkout-form" onsubmit="processCheckout(event)" class="space-y-4">
                    <div>
                        <label class="block text-sm font-medium text-gray-700">Nama Lengkap</label>
                        <input type="text" id="cust-name" required class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-pink-500 focus:ring focus:ring-pink-200 p-2 border" placeholder="Nama Kakak">
                    </div>
                    <div>
                        <label class="block text-sm font-medium text-gray-700">Alamat Lengkap</label>
                        <textarea id="cust-address" required rows="2" class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-pink-500 focus:ring focus:ring-pink-200 p-2 border" placeholder="Jalan, RT/RW, Kota..."></textarea>
                    </div>
                    <div>
                        <label class="block text-sm font-medium text-gray-700">Metode Pembayaran</label>
                        <select id="payment-method" onchange="checkPaymentMethod()" class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-pink-500 focus:ring focus:ring-pink-200 p-2 border">
                            <option value="COD">Cash / Bayar di Tempat (COD)</option>
                            <option value="DANA">E-Wallet DANA</option>
                            <option value="GOPAY">E-Wallet GoPay</option>
                            <option value="OVO">E-Wallet OVO</option>
                            <option value="SHOPEEPAY">ShopeePay</option>
                            <option value="QRIS">QRIS (Scan Barcode)</option>
                        </select>
                    </div>

                    <!-- QR Display Area -->
                    <div id="qris-container" class="hidden bg-white p-4 rounded-lg border-2 border-dashed border-gray-300 text-center">
                        <p class="text-sm text-gray-600 mb-2 font-bold">Scan QRIS di bawah ini:</p>
                        <!-- Container for QR Code -->
                        <div id="qrcode" class="flex justify-center mb-2"></div>
                        <p class="text-xs text-gray-500">Atau transfer manual via link DANA.</p>
                    </div>

                    <button type="submit" class="w-full bg-green-500 text-white font-bold py-3 rounded-lg hover:bg-green-600 transition shadow-lg flex justify-center items-center gap-2">
                        <i class="fab fa-whatsapp text-xl"></i> Kirim Pesanan ke Admin
                    </button>
                </form>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-white pt-16 pb-8 border-t-4 border-pink-300">
        <div class="container mx-auto text-center px-4">
            <h2 class="text-4xl font-cute text-pink-500 mb-2">Isty parfum</h2>
            <p class="text-xl text-gray-500 font-heading mb-8">— Teman Wangi mu! —</p>
            
            <div class="flex justify-center gap-6 mb-8">
                <a href="#" class="w-10 h-10 rounded-full bg-pink-100 flex items-center justify-center text-pink-500 hover:bg-pink-500 hover:text-white transition"><i class="fab fa-instagram"></i></a>
                <a href="#" class="w-10 h-10 rounded-full bg-pink-100 flex items-center justify-center text-pink-500 hover:bg-pink-500 hover:text-white transition"><i class="fab fa-tiktok"></i></a>
                <a href="https://wa.me/6285891693186" class="w-10 h-10 rounded-full bg-pink-100 flex items-center justify-center text-pink-500 hover:bg-pink-500 hover:text-white transition"><i class="fab fa-whatsapp"></i></a>
            </div>
            
            <p class="text-gray-400 text-sm">© 2024 Flowerss Parfum. All Rights Reserved.</p>
        </div>
    </footer>

    <!-- Scripts -->
    <script>
        // --- 1. Animation Logic (Falling Flowers) ---
        const flowerContainer = document.getElementById('flower-container');
        const flowers = ['🌸', '🌺', '🌹', '🌻', '🌼', '🌷'];

        function createFlower() {
            const flower = document.createElement('div');
            flower.classList.add('flower');
            flower.innerText = flowers[Math.floor(Math.random() * flowers.length)];
            flower.style.left = Math.random() * 100 + 'vw';
            flower.style.animationDuration = Math.random() * 3 + 2 + 's'; // 2-5 seconds
            flower.style.opacity = Math.random();
            flower.style.fontSize = Math.random() * 20 + 10 + 'px';
            
            flowerContainer.appendChild(flower);

            setTimeout(() => {
                flower.remove();
            }, 5000);
        }

        setInterval(createFlower, 300); // Create flower every 300ms


        // --- 2. Cart Logic ---
        let cart = [];
        const productsDB = [
            { id: 1, name: 'Nagita Roll', price: 7000 },
            { id: 2, name: 'Sweet Boo Roll', price: 7500 },
            { id: 3, name: 'Vanilla Cake Roll', price: 8000 }
        ];

        function addToCart(id, name, price) {
            const existingItem = cart.find(item => item.id === id);
            if (existingItem) {
                existingItem.qty++;
            } else {
                cart.push({ id, name, price, qty: 1 });
            }
            updateCartUI();
            
            // Animasi kecil saat tambah
            const btn = event.currentTarget;
            const originalText = btn.innerHTML;
            btn.innerHTML = '<i class="fas fa-check"></i> Masuk Keranjang';
            btn.classList.add('bg-green-500', 'hover:bg-green-600');
            btn.classList.remove('bg-pink-500', 'bg-purple-500', 'hover:bg-pink-600', 'hover:bg-purple-600');
            
            setTimeout(() => {
                btn.innerHTML = originalText;
                btn.classList.remove('bg-green-500', 'hover:bg-green-600');
                if(name.includes('Sweet')) btn.classList.add('bg-purple-500', 'hover:bg-purple-600');
                else btn.classList.add('bg-pink-500', 'hover:bg-pink-600');
                toggleCart(true); // Open cart immediately to show update
            }, 1000);
        }

        function removeFromCart(id) {
            cart = cart.filter(item => item.id !== id);
            updateCartUI();
        }

        function updateQty(id, change) {
            const item = cart.find(item => item.id === id);
            if (item) {
                item.qty += change;
                if (item.qty <= 0) removeFromCart(id);
                else updateCartUI();
            }
        }

        function updateCartUI() {
            const cartItemsEl = document.getElementById('cart-items');
            const cartCountEl = document.getElementById('cart-count');
            const cartTotalEl = document.getElementById('cart-total');

            // Update count badge
            const totalQty = cart.reduce((acc, item) => acc + item.qty, 0);
            cartCountEl.innerText = totalQty;

            // Calculate total price
            const totalPrice = cart.reduce((acc, item) => acc + (item.price * item.qty), 0);
            cartTotalEl.innerText = 'Rp ' + totalPrice.toLocaleString('id-ID');

            // Render Items
            if (cart.length === 0) {
                cartItemsEl.innerHTML = `
                <div class="text-center text-gray-400 mt-10">
                    <i class="fas fa-cookie-bite text-6xl mb-4 opacity-50"></i>
                    <p>Keranjang masih kosong nih, yuk jajan parfum!</p>
                </div>`;
            } else {
                cartItemsEl.innerHTML = cart.map(item => `
                    <div class="flex justify-between items-center mb-4 border-b border-gray-100 pb-2">
                        <div>
                            <h4 class="font-bold text-gray-800">${item.name}</h4>
                            <div class="text-xs text-gray-500">Rp ${item.price.toLocaleString('id-ID')}</div>
                        </div>
                        <div class="flex items-center gap-2">
                            <button onclick="updateQty(${item.id}, -1)" class="w-6 h-6 bg-gray-200 rounded-full text-gray-600 hover:bg-gray-300">-</button>
                            <span class="font-bold w-4 text-center">${item.qty}</span>
                            <button onclick="updateQty(${item.id}, 1)" class="w-6 h-6 bg-pink-200 rounded-full text-pink-600 hover:bg-pink-300">+</button>
                            <button onclick="removeFromCart(${item.id})" class="ml-2 text-red-400 hover:text-red-600"><i class="fas fa-trash"></i></button>
                        </div>
                    </div>
                `).join('');
            }
        }

        // --- 3. UI Toggles ---
        function toggleCart(forceOpen = false) {
            const modal = document.getElementById('cart-modal');
            const panel = document.getElementById('cart-panel');
            
            if (modal.classList.contains('hidden') || forceOpen) {
                modal.classList.remove('hidden');
                // Small delay for slide animation
                setTimeout(() => {
                    panel.classList.remove('translate-x-full');
                }, 10);
            } else {
                panel.classList.add('translate-x-full');
                setTimeout(() => {
                    modal.classList.add('hidden');
                }, 300);
            }
        }

        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        }

        // --- 4. QRIS Generator Logic ---
        let qrCodeObj = null;

        function checkPaymentMethod() {
            const method = document.getElementById('payment-method').value;
            const qrisContainer = document.getElementById('qris-container');
            const qrTarget = document.getElementById('qrcode');
            
            // URL DANA yang diberikan user
            // Format deep link DANA untuk QRIS/Request Money
            const danaUrl = "https://link.dana.id/minta?full_url=https://qr.dana.id/v1/281012012024110773006713";

            if (method === 'QRIS') {
                qrisContainer.classList.remove('hidden');
                qrTarget.innerHTML = ""; // Clear previous QR
                
                // Generate QR Code baru
                if (!qrCodeObj) {
                     new QRCode(qrTarget, {
                        text: danaUrl,
                        width: 128,
                        height: 128,
                        colorDark : "#000000",
                        colorLight : "#ffffff",
                        correctLevel : QRCode.CorrectLevel.H
                    });
                } else {
                    qrTarget.innerHTML = "";
                    new QRCode(qrTarget, {
                        text: danaUrl,
                        width: 128,
                        height: 128
                    });
                }
            } else {
                qrisContainer.classList.add('hidden');
            }
        }

        // --- 5. Checkout Process (WhatsApp) ---
        function processCheckout(e) {
            e.preventDefault();
            
            if (cart.length === 0) {
                alert("Keranjang masih kosong, pilih parfum dulu ya kak!");
                return;
            }

            const name = document.getElementById('cust-name').value;
            const address = document.getElementById('cust-address').value;
            const payment = document.getElementById('payment-method').value;
            
            // Hitung Total
            const totalPrice = cart.reduce((acc, item) => acc + (item.price * item.qty), 0);
            const totalFormatted = totalPrice.toLocaleString('id-ID');

            // Format List Barang
            let itemList = "";
            cart.forEach((item, index) => {
                itemList += `${index + 1}. ${item.name} (${item.qty}x) - Rp ${(item.price * item.qty).toLocaleString('id-ID')}%0A`;
            });

            // Format Pesan WhatsApp
            const message = `Halo Admin *Isty Parfum*! 🌸%0A%0ASaya mau pesan parfum roll dong:%0A--------------------------------%0A${itemList}--------------------------------%0A*Total: Rp ${totalFormatted}*%0A%0A📝 *Data Pemesan:*%0ANama: ${name}%0AAlamat: ${address}%0AMetode Bayar: ${payment}%0A%0AMohon diproses ya kak! Terima kasih ✨`;

            // Nomor WA Admin
            const phoneNumber = "6285891693186";
            
            // Redirect ke WA
            const waUrl = `https://wa.me/${phoneNumber}?text=${message}`;
            window.open(waUrl, '_blank');
        }

    </script>
</body>
</html>
