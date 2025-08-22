<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>iGarden by Fairland | The Future of Pool Cleaning</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Minimalist Sky Blue & Slate -->
    <!-- Application Structure Plan: The SPA is designed as a single-page narrative to guide potential partners through a compelling business pitch. The structure follows a classic persuasive flow: 1. Hook (Hero & Market Opportunity), 2. Agitate (User Pain Points), 3. Solution (iGarden's core features), 4. Credibility (About Us, Timeline, Team), and 5. Call to Action. This top-down, story-driven architecture is more engaging and effective for a B2B audience than a fragmented, dashboard-style layout, as it builds a logical case for partnership step-by-step. User flow is linear via scrolling, supported by a sticky navigation bar for quick access to key sections. -->
    <!-- Visualization & Content Choices: 1. Global Market (Donut Chart): Goal: Instantly show the large untapped market. Method: Chart.js Donut. Interaction: Tooltip on hover. Justification: Best for part-to-whole data. 2. US Market Trend (Line Chart): Goal: Show growth and compare US vs. Global penetration. Method: Chart.js Line. Interaction: Tooltip. Justification: Ideal for time-series comparison. 3. Cleaning Methods (Bar Chart): Goal: Position robotic cleaners against traditional methods. Method: Chart.js Bar. Interaction: Tooltip. Justification: Clear for categorical comparison. 4. Endurance Comparison (Bar Chart): Goal: Highlight iGarden's key competitive advantage. Method: Chart.js Bar with animation. Justification: High-impact visual for a direct feature comparison. 5. 3D S-Path (Animated Diagram): Goal: Simplify a complex technical feature. Method: Custom JS/CSS animation. Justification: More engaging and understandable than a static diagram. 6. Company Timeline (Vertical Layout): Goal: Build credibility and show history of innovation. Method: HTML/CSS with scroll-triggered animations. Justification: Interactive storytelling that avoids clutter. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #F1F5F9;
            color: #334155;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            height: 320px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 400px;
            }
        }
        .nav-link {
            transition: color 0.3s ease;
            position: relative;
            padding-bottom: 4px;
        }
        .nav-link::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background-color: #3B82F6;
            transition: width 0.3s ease;
        }
        .nav-link.active, .nav-link:hover {
            color: #3B82F6;
        }
        .nav-link.active::after, .nav-link:hover::after {
            width: 100%;
        }
        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }
        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
        .path-dot {
            position: absolute;
            width: 12px;
            height: 12px;
            background-color: #3B82F6;
            border-radius: 50%;
            box-shadow: 0 0 8px #3B82F6;
        }
        .product-image {
            width: 128px; /* 1/3 of 384px */
            height: 128px; /* 1/3 of 384px */
            object-fit: cover;
        }
        @media (min-width: 640px) {
            .product-image {
                width: 160px; /* 1/3 of 480px */
                height: 160px; /* 1/3 of 480px */
            }
        }
    </style>
</head>
<body class="antialiased">

    <header id="header" class="bg-white/80 backdrop-blur-lg fixed top-0 left-0 right-0 z-50 shadow-lg">
        <nav class="container mx-auto px-6 py-4 flex justify-between items-center">
            <div class="text-2xl font-bold text-slate-900">
                <span class="text-sky-600">iGarden</span> by Fairland
            </div>
            <div class="hidden md:flex space-x-8">
                <a href="#opportunity" class="nav-link text-slate-600 font-medium">Market Opportunity</a>
                <a href="#us-market" class="nav-link text-slate-600 font-medium">US Market</a>
                <a href="#problem" class="nav-link text-slate-600 font-medium">User Pain Points</a>
                <a href="#solution" class="nav-link text-slate-600 font-medium">Our Solution</a>
                <a href="#video-demo" class="nav-link text-slate-600 font-medium">Product Demo</a>
                <a href="#about" class="nav-link text-slate-600 font-medium">About Us</a>
                <a href="#team" class="nav-link text-slate-600 font-medium">Our Team</a>
            </div>
            <a href="#contact-us" class="hidden md:inline-block bg-sky-600 text-white font-bold py-2 px-6 rounded-full shadow-lg transition-transform hover:scale-105">Get in Touch</a>
            <button id="mobile-menu-button" class="md:hidden text-slate-600 focus:outline-none">
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path></svg>
            </button>
        </nav>
        <div id="mobile-menu" class="hidden md:hidden bg-white">
            <a href="#opportunity" class="block py-2 px-4 text-sm text-slate-600 hover:bg-slate-100">Market Opportunity</a>
            <a href="#us-market" class="block py-2 px-4 text-sm text-slate-600 hover:bg-slate-100">US Market</a>
            <a href="#problem" class="block py-2 px-4 text-sm text-slate-600 hover:bg-slate-100">User Pain Points</a>
            <a href="#solution" class="block py-2 px-4 text-sm text-slate-600 hover:bg-slate-100">Our Solution</a>
            <a href="#video-demo" class="block py-2 px-4 text-sm text-slate-600 hover:bg-slate-100">Product Demo</a>
            <a href="#about" class="block py-2 px-4 text-sm text-slate-600 hover:bg-slate-100">About Us</a>
            <a href="#team" class="block py-2 px-4 text-sm text-slate-600 hover:bg-slate-100">Our Team</a>
            <a href="#contact-us" class="block py-2 px-4 text-sm bg-sky-600 text-white hover:bg-sky-700 text-center">Get in Touch</a>
        </div>
    </header>

    <main>
        <section id="hero" class="pt-32 pb-20 bg-white">
            <div class="container mx-auto px-6 text-center">
                <h1 class="text-4xl md:text-6xl font-bold text-slate-900 leading-tight mb-4 fade-in">The Wireless Revolution in Pool Cleaning</h1>
                <p class="text-lg md:text-xl text-slate-600 max-w-3xl mx-auto fade-in" style="transition-delay: 0.2s;">We believe the best moments are spent enjoying life, not cleaning up. That's why we created iGarden by Fairland, the world’s longest-running AI wireless robot, designed to give you the freedom you deserve and the pristine cleanliness you expect.</p>
                <img src="https://www.fairlandgroup.com/core/extend/kindeditor/attached/image/20250227/20250227102305_35364.jpg" alt="iGarden AI Wireless Robot" class="mx-auto rounded-lg shadow-md mt-12 mb-8 max-w-lg sm:max-w-xl lg:max-w-2xl fade-in" style="transition-delay: 0.4s;">
            </div>
        </section>

        <section id="opportunity" class="py-20 bg-slate-100">
            <div class="container mx-auto px-6">
                <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold text-slate-900 mb-4 fade-in">A Vast Blue Ocean Opportunity</h2>
                    <p class="text-lg text-slate-600 max-w-3xl mx-auto fade-in">The global pool market is immense, but the penetration of robotic cleaners is still low. This presents a huge, untapped opportunity for a truly superior product.</p>
                    <p class="text-lg text-slate-600 max-w-4xl mx-auto mt-6 fade-in" style="transition-delay: 0.2s;">With over 40 million pools worldwide and a continuously growing market, the low penetration of robotic cleaners (only 23%) means a massive 77% of the market is still waiting to be claimed, presenting a vast "blue ocean" opportunity for an innovative product like iGarden.</p>
                </div>
                <div class="grid md:grid-cols-2 gap-8 lg:gap-16 items-center">
                    <div class="fade-in">
                        <h3 class="text-2xl font-semibold text-slate-800 mb-4 text-center">Untapped Potential</h3>
                        <div class="chart-container h-80 md:h-96">
                            <canvas id="marketPenetrationChart"></canvas>
                        </div>
                        <p class="text-center mt-4 text-slate-600">The chart shows over 40 million pools worldwide. With only 23% of pools using a robot, 77% of the market is waiting for an innovative solution.</p>
                        <div class="text-center mt-8">
                             <a href="mailto:brandon@fairland.com.cn" class="inline-block bg-sky-600 text-white font-bold py-3 px-8 rounded-full shadow-lg transition-transform hover:scale-105">Partner with Us</a>
                        </div>
                    </div>
                    <div class="fade-in">
                        <h3 class="text-2xl font-semibold text-slate-800 mb-4 text-center">Current Pool Cleaning Methods</h3>
                        <div class="chart-container h-80 md:h-96">
                            <canvas id="cleaningMethodsChart"></canvas>
                        </div>
                        <p class="text-center mt-4 text-slate-600">Manual and suction cleaning methods still dominate, but they are inefficient and time-consuming. This highlights the urgent need for a more convenient, automated alternative.</p>
                    </div>
                </div>
                <img src="https://store.igarden.ai/cdn/shop/files/K__Amazon_Listing_1600x901-3.png?v=1752054710" alt="Global Pool Market Segmentation" class="mx-auto rounded-lg shadow-md mt-12 mb-8 fade-in">
            </div>
        </section>
        
        <section id="us-market" class="py-20 bg-white">
            <div class="container mx-auto px-6 text-center">
                <h2 class="text-3xl md:text-4xl font-bold text-slate-900 mb-4 fade-in">Unlocking the American Market: The Power of iGarden</h2>
                <p class="text-lg text-slate-600 max-w-3xl mx-auto fade-in">As the world's largest pool market, the United States has over 10.4 million residential swimming pools. This vast user base and continuous growth trend present an unparalleled "blue ocean" opportunity for smart pool robots.</p>
                <div class="mt-12 mb-8 fade-in">
                     <img src="https://store.igarden.ai/cdn/shop/files/790_790_7abc0f42-2d57-4630-83e0-42576211b857.jpg?v=1754298479" alt="Pools in the US" class="mx-auto rounded-lg shadow-md">
                </div>
                <div class="grid md:grid-cols-2 gap-8 lg:gap-16 items-center mt-12">
                    <div class="fade-in">
                        <h3 class="text-2xl font-semibold text-slate-800 mb-4 text-center">US Pool Market vs. Robotic Cleaner Penetration</h3>
                        <div class="chart-container h-80 md:h-96">
                            <canvas id="usMarketChart"></canvas>
                        </div>
                        <p class="text-center mt-4 text-slate-600">While the US has the most pools globally, there is still immense room for growth in robotic cleaner penetration—a perfect opportunity for iGarden.</p>
                    </div>
                    <div class="fade-in">
                        <h3 class="text-2xl font-semibold text-slate-800 mb-4 text-center">Why iGarden Is Perfect for the US Market</h3>
                        <div class="space-y-6 text-left">
                            <div class="p-6 rounded-lg bg-slate-100 shadow-sm">
                                <h4 class="text-xl font-semibold text-slate-900 mb-2">Unmatched Endurance for American Pools</h4>
                                <p class="text-slate-600">US pools are often larger, requiring exceptional endurance. iGarden, with its world-record battery life, perfectly addresses this pain point, ensuring even large pools are cleaned in a single session for a truly hassle-free experience.</p>
                            </div>
                            <div class="p-6 rounded-lg bg-slate-100 shadow-sm">
                                <h4 class="text-xl font-semibold text-slate-900 mb-2">Advanced AI Built for US Consumers</h4>
                                <p class="text-slate-600">US consumers are highly receptive to smart home and automation products. iGarden's AI wireless technology, intelligent path planning, and mobile app control precisely meet this market demand, offering a more efficient and modern approach to pool maintenance.</p>
                            </div>
                            <div class="p-6 rounded-lg bg-slate-100 shadow-sm">
                                <h4 class="text-xl font-semibold text-slate-900 mb-2">Reliability and Service Built on Trust</h4>
                                <p class="text-slate-600">We know that quality and service are key to winning the market. iGarden's extremely low repair rate and Fairland's global service network ensure we can provide fast, reliable support to our US partners and end-users, building long-term trust.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="problem" class="py-20 bg-slate-100">
            <div class="container mx-auto px-6">
                <div class="text-center mb-12">
                    <h2 class="text-3xl md::text-4xl font-bold text-slate-900 mb-4 fade-in">The Hidden Hassles of Pool Ownership</h2>
                    <p class="text-lg text-slate-600 max-w-3xl mx-auto fade-in">Imagine you finally have a relaxing weekend, only to be frustrated by your pool cleaner. We listened to countless user complaints and designed iGarden to eliminate these common annoyances.</p>
                </div>
                <div class="grid md:grid-cols-3 gap-8 text-center">
                    <div class="bg-white p-8 rounded-lg shadow-md fade-in">
                        <div class="text-4xl mb-4">🔋</div>
                        <h3 class="text-xl font-semibold text-slate-900 mb-2">Mid-Clean Shutdowns</h3>
                        <p class="text-slate-600">A typical cleaner runs out of battery halfway through a job. You're left with an unfinished task and hours of waiting for it to recharge. It's a chore, not a convenience.</p>
                    </div>
                    <div class="bg-white p-8 rounded-lg shadow-md fade-in" style="transition-delay: 0.2s;">
                        <div class="text-4xl mb-4">🔌</div>
                        <h3 class="text-xl font-semibold text-slate-900 mb-2">Tangled Cords</h3>
                        <p class="text-slate-600">A corded robot is supposed to be simple, but the tangled cords limit its cleaning range and make storage a nightmare. It robs you of the effortless pool experience you crave.</p>
                    </div>
                    <div class="bg-white p-8 rounded-lg shadow-md text-center fade-in" style="transition-delay: 0.4s;">
                        <div class="text-4xl mb-4">🧩</div>
                        <h3 class="text-xl font-semibold text-slate-900 mb-2">Missed Spots</h3>
                        <p class="text-slate-600">Many robots follow a random, chaotic path, leaving parts of the pool untouched. This means you have to finish the job manually, which defeats the purpose of an automated cleaner.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="solution" class="py-20 bg-white">
            <div class="container mx-auto px-6">
                <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold text-slate-900 mb-4 fade-in">The iGarden Solution: Built for True Freedom</h2>
                    <p class="text-lg text-slate-600 max-w-3xl mx-auto fade-in">Our AI wireless robotic cleaner is built on three pillars of innovation, designed to provide a truly autonomous and superior cleaning experience.</p>
                </div>
                <div class="grid lg:grid-cols-3 gap-8">
                    <div class="bg-slate-100 p-8 rounded-lg shadow-lg border border-slate-200 fade-in">
                        <div class="flex items-center mb-4">
                            <div class="text-3xl mr-4">🏆</div>
                            <h3 class="text-2xl font-semibold text-slate-900">Unparalleled Endurance</h3>
                        </div>
                        <p class="text-slate-600 mb-4">With our patented <strong class="text-slate-800">Full-inverter Technology</strong>, the iGarden robot can run for up to 10 hours on a single charge—four times the industry average. Our prototype even set a Guinness World Record for 40 hours, a testament to our technological leadership.</p>
                        <p class="text-slate-600 mb-6 font-medium">This world record is more than just a number. It means iGarden can complete a thorough cleaning of an Olympic-sized pool on a single charge, without interruption, completely solving the "unfinished job" pain point.</p>
                        <div class="chart-container h-64">
                            <canvas id="enduranceChart"></canvas>
                        </div>
                        <img src="https://www.fairlandgroup.com/core/extend/kindeditor/attached/image/20250227/20250227102305_35364.jpg" alt="Guinness World Record" class="mx-auto rounded-lg shadow-md mt-6">
                    </div>
                    <div class="bg-slate-100 p-8 rounded-lg shadow-lg border border-slate-200 fade-in" style="transition-delay: 0.2s;">
                        <div class="flex items-center mb-4">
                            <div class="text-3xl mr-4">🎯</div>
                            <h3 class="text-2xl font-semibold text-slate-900">Revolutionary Cleaning Efficiency</h3>
                        </div>
                        <p class="text-slate-600 mb-6">Utilizing 7 advanced sensors and smart navigation, our robot plans the most effective <strong class="text-slate-800">3D S-Path</strong>. This ensures a cleaning efficiency twice that of random-path cleaners, leaving no area missed.</p>
                        <div id="path-animation-container" class="relative w-full h-64 bg-white rounded-lg overflow-hidden flex items-center justify-center">
                            <div class="absolute inset-0 border-4 border-slate-300 rounded-lg"></div>
                            <div class="path-dot"></div>
                            <div id="coverage-counter" class="absolute bottom-4 right-4 text-slate-600 font-bold text-xl">Coverage: 0%</div>
                            <div class="absolute top-2 left-2 text-sky-600 font-semibold">"3D S-Path" Animation Demo</div>
                        </div>
                        <img src="https://store.igarden.ai/cdn/shop/files/790_790_7abc0f42-2d57-4630-83e0-42576211b857.jpg?v=1754298479" alt="3D S-Path Diagram" class="mx-auto rounded-lg shadow-md mt-6">
                    </div>
                    <div class="bg-slate-100 p-8 rounded-lg shadow-lg border border-slate-200 fade-in" style="transition-delay: 0.4s;">
                        <div class="flex items-center mb-4">
                            <div class="text-3xl mr-4">🛡️</div>
                            <h3 class="text-2xl font-semibold text-slate-900">Uncompromising Quality</h3>
                        </div>
                        <p class="text-slate-600 mb-6">We strive for a near-zero failure rate through extreme testing. With motor housings tested in 6-meter-deep water, and over 50,000 units shipped, our failure rate is below 0.7%, setting a new standard for reliability.</p>
                        <div class="space-y-4">
                            <div class="bg-white p-4 rounded-lg">
                                <p class="font-semibold text-slate-900">Extreme Waterproofing</p>
                                <p class="text-sm text-slate-600">Tested to be durable in depths of 9 meters.</p>
                            </div>
                            <div class="bg-white p-4 rounded-lg">
                                <p class="font-semibold text-semibold text-slate-900">Industry-Leading Reliability</p>
                                <p class="text-sm text-slate-600">Failure rate below 0.7%, far below the industry average of 3-5%.</p>
                            </div>
                            <div class="bg-white p-4 rounded-lg">
                                <p class="font-semibold text-semibold text-slate-900">AI Smart Scheduling</p>
                                <p class="text-sm text-slate-600">Set a cleaning schedule for up to two weeks on a single charge.</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="mt-20 text-center fade-in">
                    <h2 class="text-3xl md:text-4xl font-bold text-slate-900 mb-4">iGarden K Series: Our Product Line</h2>
                    <p class="text-lg text-slate-600 max-w-3xl mx-auto mb-8">The iGarden K Series is a line of AI wireless robots designed specifically for the global residential pool market. The series is built to meet the needs of various users, from basic functionality to advanced smart cleaning, all in one product.</p>
                    <div class="flex flex-wrap justify-center mt-12 gap-8">
                        <div class="bg-slate-100 p-6 rounded-lg shadow-lg border border-slate-200 w-full sm:w-60 transition-all hover:scale-105">
                            <img src="https://store.igarden.ai/cdn/shop/files/D1.jpg?v=1754298479" alt="iGarden K25 Robot" class="product-image mx-auto rounded-lg mb-4">
                            <h3 class="text-xl font-semibold text-slate-900 mb-2">iGarden K25</h3>
                            <p class="text-slate-500 text-sm mb-4">Entry-level model, ideal for smaller pools.</p>
                            <ul class="text-slate-600 text-left list-disc list-inside space-y-1">
                                <li>Basic cleaning functions</li>
                                <li>Lightweight design</li>
                                <li>Great value</li>
                            </ul>
                        </div>
                        <div class="bg-slate-100 p-6 rounded-lg shadow-lg border border-slate-200 w-full sm:w-60 transition-all hover:scale-105">
                            <img src="https://store.igarden.ai/cdn/shop/files/D1.jpg?v=1754298479" alt="iGarden K40 Robot" class="product-image mx-auto rounded-lg mb-4">
                            <h3 class="text-xl font-semibold text-slate-900 mb-2">iGarden K40</h3>
                            <p class="text-slate-500 text-sm mb-4">Mainstream model, balancing performance and price.</p>
                            <ul class="text-slate-600 text-left list-disc list-inside space-y-1">
                                <li>Smart path planning</li>
                                <li>High cleaning efficiency</li>
                                <li>Suitable for medium pools</li>
                            </ul>
                        </div>
                        <div class="bg-slate-100 p-6 rounded-lg shadow-lg border border-slate-200 w-full sm:w-60 transition-all hover:scale-105">
                            <img src="https://store.igarden.ai/cdn/shop/files/KV-6H-790_790_6343dfa1-f3ef-4955-9843-8b4a50e56078.jpg?v=1754298479" alt="iGarden K60 Robot" class="product-image mx-auto rounded-lg mb-4">
                            <h3 class="text-xl font-semibold text-slate-900 mb-2">iGarden K60</h3>
                            <p class="text-slate-500 text-sm mb-4">High-performance model, offering a superior cleaning experience.</p>
                            <ul class="text-slate-600 text-left list-disc list-inside space-y-1">
                                <li>3D S-path planning</li>
                                <li>Longest runtime</li>
                                <li>AI smart features</li>
                            </ul>
                        </div>
                        <div class="bg-slate-100 p-6 rounded-lg shadow-lg border border-slate-200 w-full sm:w-60 transition-all hover:scale-105">
                            <img src="https://store.igarden.ai/cdn/shop/files/K80.jpg?v=1754298479" alt="iGarden K80 Robot" class="product-image mx-auto rounded-lg mb-4">
                            <h3 class="text-xl font-semibold text-slate-900 mb-2">iGarden K80</h3>
                            <p class="text-slate-500 text-sm mb-4">Flagship model, designed for large pools.</p>
                            <ul class="text-slate-600 text-left list-disc list-inside space-y-1">
                                <li>Full-featured smart navigation</li>
                                <li>Extended endurance</li>
                                <li>Remote app control</li>
                            </ul>
                        </div>
                    </div>
                    <a href="https://store.igarden.ai" target="_blank" class="mt-12 inline-block bg-sky-600 text-white font-bold py-3 px-8 rounded-full shadow-lg transition-transform hover:scale-105">Explore Our Products</a>
                </div>
            </div>
        </section>

        <section id="video-demo" class="py-20 bg-slate-100">
            <div class="container mx-auto px-6 text-center">
                <h2 class="text-3xl md:text-4xl font-bold text-slate-900 mb-4 fade-in">See It to Believe It: iGarden in Action</h2>
                <p class="text-lg text-slate-600 max-w-3xl mx-auto mb-12 fade-in">Watch our AI wireless pool robot effortlessly handle any cleaning challenge.</p>
                <div class="aspect-w-16 aspect-h-9 max-w-4xl mx-auto rounded-lg overflow-hidden shadow-2xl fade-in">
                    <iframe src="https://www.youtube.com/embed/IKWYKOB_zck" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                </div>
            </div>
        </section>

        <section id="about" class="py-20 bg-white">
            <div class="container mx-auto px-6">
                <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold text-slate-900 mb-4 fade-in">26 Years of Innovation: The Fairland Story</h2>
                    <p class="text-lg text-slate-600 max-w-3xl mx-auto fade-in">iGarden is a product of Fairland’s technological heritage, born with the mission to deliver extraordinary value. For over two decades, we have not only pushed the boundaries of outdoor technology—growing the pool heat pump industry from a $100 million to a $1.2 billion market—but also forged strong global partnerships and a commitment to superior customer service. This DNA of innovation and service is deeply embedded in the iGarden robot.</p>
                </div>
                <div class="text-center mb-12 fade-in">
                    <h3 class="text-2xl font-semibold text-slate-800 mb-4">From Heat Pumps to Robots: A Shared Technical Heritage</h3>
                    <p class="text-slate-600 max-w-4xl mx-auto">As a leader in pool heat pumps, Fairland revolutionized the industry with our groundbreaking <strong class="text-slate-800">Full-inverter Technology</strong> and <strong class="text-slate-800">HP-Booster Technology</strong>. These innovations dramatically improved energy efficiency and performance, gaining widespread market recognition. The same core philosophy of 'creating more value with less energy' drives iGarden, making it the most energy-efficient and longest-running robot on the market.</p>
                </div>

                <div class="text-center mb-12 fade-in">
                    <h3 class="text-2xl font-semibold text-slate-800 mb-4">Partnering for the Future: Our Global Network and Service Promise</h3>
                    <p class="text-slate-600 max-w-4xl mx-auto">Our success is built not just on technology, but on our global partnerships and unwavering commitment to customers. We collaborate with leading distributors in over 50 countries and regions, including the Americas, Europe, and Australia, to ensure our products reach connoisseurs worldwide. This network is founded on the philosophy of “extreme customer service,” where we provide swift and comprehensive support to both our partners and end-users. We believe in building long-term relationships and a shared ecosystem of success, which solidifies our mission to create an easier, more enjoyable life for pool owners everywhere.</p>
                    <blockquote class="mt-8 text-xl italic font-medium text-slate-700 bg-slate-100 p-6 rounded-lg shadow-inner">
                        <p>"Fairland's commitment to service and innovation is second to none. Their team's support has been instrumental to our success. The iGarden is a game-changer."</p>
                        <footer class="mt-4 text-sm text-slate-500">— Frédéric Lachance, US Distributor Partner</footer>
                    </blockquote>
                    <div class="flex flex-wrap justify-center mt-6 gap-4">
                         <a href="https://www.fairlandgroup.com/global-partners?locale=en" target="_blank" class="inline-block bg-sky-600 text-white font-bold py-2 px-6 rounded-full shadow-lg transition-transform hover:scale-105">View Our Global Partners</a>
                         <a href="https://www.720yun.com/vr/59ejO5masy5" target="_blank" class="inline-block bg-slate-600 text-white font-bold py-2 px-6 rounded-full shadow-lg transition-transform hover:scale-105">Explore Our Showrooms</a>
                    </div>
                </div>

                <div class="text-center my-12 fade-in">
                    <h3 class="text-2xl md:text-3xl font-bold text-slate-900 mb-4">
                        Your Success is Our Mission: Sales Support
                    </h3>
                    <p class="text-lg text-slate-600 max-w-3xl mx-auto mb-8">
                        We firmly believe that strong partnerships are built on mutual trust. For every distributor, we provide not only exceptional products but also comprehensive sales support to ensure your success in the market. We are committed to being your most reliable partner, making your sales journey smooth and efficient.
                    </p>
                    <div class="grid md:grid-cols-3 gap-8">
                        <div class="bg-slate-100 p-8 rounded-lg shadow-md flex flex-col items-center">
                            <div class="text-4xl mb-4 text-sky-600">🚀</div>
                            <h4 class="text-xl font-semibold text-slate-900 mb-2">Comprehensive Marketing & Branding Support</h4>
                            <p class="text-slate-600 text-sm mb-4">
                                Providing full marketing resources (images, videos, presentations).
                            </p>
                            <p class="text-slate-600 text-sm">
                                Official brand authorization and co-branding opportunities.
                            </p>
                        </div>
                        <div class="bg-slate-100 p-8 rounded-lg shadow-md flex flex-col items-center">
                            <div class="text-4xl mb-4 text-sky-600">🎓</div>
                            <h4 class="text-xl font-semibold text-slate-900 mb-2">Expertise & Training</h4>
                            <p class="text-slate-600 text-sm mb-4">
                                Offering regular product training for your team.
                            </p>
                            <p class="text-slate-600 text-sm">
                                Professional consultation and technical support.
                            </p>
                        </div>
                        <div class="bg-slate-100 p-8 rounded-lg shadow-md flex flex-col items-center">
                            <div class="text-4xl mb-4 text-sky-600">🤝</div>
                            <h4 class="text-xl font-semibold text-slate-900 mb-2">Flexible Policies & Premium Service</h4>
                            <p class="text-slate-600 text-sm mb-4">
                                Competitive pricing strategy and generous profit margins.
                            </p>
                            <p class="text-slate-600 text-sm">
                                Efficient logistics and professional after-sales support.
                            </p>
                        </div>
                    </div>
                </div>

                <div class="relative max-w-2xl mx-auto">
                    <!-- Updated image size: max-w-lg from max-w-2xl -->
                    <img src="https://www.fairlandgroup.com/static/upload/image/20250124/1737707234774539.jpg" alt="Fairland Products" class="mx-auto rounded-lg shadow-md mb-8 max-w-3xl">
                    <div class="relative">
                        <div class="absolute left-1/2 h-full w-0.5 bg-slate-300 transform -translate-x-1/2"></div>
                        <div class="space-y-12">
                            <div class="relative fade-in">
                                <div class="absolute left-1/2 top-1/2 w-4 h-4 bg-sky-600 rounded-full transform -translate-x-1/2 -translate-y-1/2 border-4 border-white"></div>
                                <div class="flex items-center justify-start md:justify-end md:text-right">
                                    <div class="md:w-5/12 p-4">
                                        <p class="text-lg font-bold text-sky-600">1999</p>
                                        <h3 class="text-xl font-semibold text-slate-900">Fairland Brand Established</h3>
                                        <p class="text-slate-600">Our journey of innovation begins.</p>
                                    </div>
                                </div>
                            </div>
                            <div class="relative fade-in">
                                <div class="absolute left-1/2 top-1/2 w-4 h-4 bg-sky-600 rounded-full transform -translate-x-1/2 -translate-y-1/2 border-4 border-white"></div>
                                <div class="flex items-center justify-start">
                                     <div class="md:w-5/12 md:ml-auto p-4">
                                        <p class="text-lg font-bold text-sky-600">2012</p>
                                        <h3 class="text-xl font-semibold text-slate-900">HP-Booster Technology</h3>
                                        <p class="text-slate-600">Our first energy optimization technology, providing heat pumps with higher performance.</p>
                                    </div>
                                </div>
                            </div>
                            <div class="relative fade-in">
                                <div class="absolute left-1/2 top-1/2 w-4 h-4 bg-sky-600 rounded-full transform -translate-x-1/2 -translate-y-1/2 border-4 border-white"></div>
                                <div class="flex items-center justify-start md:justify-end md:text-right">
                                    <div class="md:w-5/12 p-4">
                                        <p class="text-lg font-bold text-sky-600">2014</p>
                                        <h3 class="text-xl font-semibold text-slate-900">Full-inverter Technology</h3>
                                        <p class="text-slate-600">A revolutionary technology that transformed pool heating efficiency.</p>
                                    </div>
                                </div>
                            </div>
                            <div class="relative fade-in">
                                <div class="absolute left-1/2 top-1/2 w-4 h-4 bg-sky-600 rounded-full transform -translate-x-1/2 -translate-y-1/2 border-4 border-white"></div>
                                <div class="flex items-center justify-start">
                                    <div class="md:w-5/12 md:ml-auto p-4">
                                        <p class="text-lg font-bold text-sky-600">2023</p>
                                        <h3 class="text-xl font-semibold text-slate-900">AI Wireless Robot Launch</h3>
                                        <p class="text-slate-600">After 7 years of R&D, iGarden is officially launched, with over 50,000 units shipped in the first year.</p>
                                    </div>
                                </div>
                            </div>
                            <div class="relative fade-in">
                                <div class="absolute left-1/2 top-1/2 w-4 h-4 bg-sky-600 rounded-full transform -translate-x-1/2 -translate-y-1/2 border-4 border-white"></div>
                                <div class="flex items-center justify-start md:justify-end md:text-right">
                                    <div class="md:w-5/12 p-4">
                                        <p class="text-lg font-bold text-sky-600">2024</p>
                                        <h3 class="text-xl font-semibold text-slate-900">Guinness World Record</h3>
                                        <p class="text-slate-600">We set the world record for the longest operating time, solidifying our leading position.</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Team Section -->
        <section id="team" class="py-20 bg-slate-100">
            <div class="container mx-auto px-6">
                <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold text-slate-900 mb-4 fade-in">Our Team</h2>
                    <p class="text-lg text-slate-600 max-w-3xl mx-auto fade-in">The driving force behind the iGarden innovation and success.</p>
                </div>
                <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
                    <!-- Team Member 1 -->
                    <div class="bg-white p-6 rounded-lg shadow-md flex flex-col items-center text-center fade-in">
                        <img src="https://play-lh.googleusercontent.com/xyKYk94czuOe_N_NDgYFg5RnD-dx4DkZOHX7DNfXXgjPCeCx_Lmv1XpOuTOzXVVYyGA" alt="Team member Andy Chen" class="w-40 h-40 rounded-full mb-4 object-cover">
                        <h3 class="text-xl font-semibold text-slate-900 mb-1">Andy Chen</h3>
                        <p class="text-sky-600 font-medium text-sm">CEO & Founder</p>
                        <p class="text-slate-600 text-sm mt-2 italic">"Driven by a 'stupid' dream, we invest in technology to create an 'Innovation Utopia' for a smarter outdoor life."</p>
                    </div>
                    <!-- Team Member 2 -->
                    <div class="bg-white p-6 rounded-lg shadow-md flex flex-col items-center text-center fade-in" style="transition-delay: 0.2s;">
                        <img src="https://play-lh.googleusercontent.com/xyKYk94czuOe_N_NDgYFg5RnD-dx4DkZOHX7DNfXXgjPCeCx_Lmv1XpOuTOzXVVYyGA" alt="Team member Zheng Chengdong" class="w-40 h-40 rounded-full mb-4 object-cover">
                        <h3 class="text-xl font-semibold text-slate-900 mb-1">Zheng Chengdong</h3>
                        <p class="text-sky-600 font-medium text-sm">Head of R&D</p>
                        <p class="text-slate-600 text-sm mt-2 italic">"We leverage our Full-inverter heritage to pioneer AI-wireless technology, ensuring an ultimate customer experience."</p>
                    </div>
                    <!-- Team Member 3 -->
                    <div class="bg-white p-6 rounded-lg shadow-md flex flex-col items-center text-center fade-in" style="transition-delay: 0.4s;">
                        <img src="https://play-lh.googleusercontent.com/xyKYk94czuOe_N_NDgYFg5RnD-dx4DkZOHX7DNfXXgjPCeCx_Lmv1XpOuTOzXVVYyGA" alt="Team member Cao Zhiling" class="w-40 h-40 rounded-full mb-4 object-cover">
                        <h3 class="text-xl font-semibold text-slate-900 mb-1">Cao Zhiling</h3>
                        <p class="text-sky-600 font-medium text-sm">Head of Product</p>
                        <p class="text-slate-600 text-sm mt-2 italic">"By building win-win partnerships, we aim to deliver products that bring tangible value to every user, everywhere."</p>
                    </div>
                    <!-- Team Member 4 -->
                    <div class="bg-white p-6 rounded-lg shadow-md flex flex-col items-center text-center fade-in" style="transition-delay: 0.6s;">
                        <img src="https://play-lh.googleusercontent.com/xyKYk94czuOe_N_NDgYFg5RnD-dx4DkZOHX7DNfXXgjPCeCx_Lmv1XpOuTOzXVVYyGA" alt="Team member Eva Tang" class="w-40 h-40 rounded-full mb-4 object-cover">
                        <h3 class="text-xl font-semibold text-slate-900 mb-1">Eva Tang</h3>
                        <p class="text-sky-600 font-medium text-sm">AI-wireless Robot Sales Director</p>
                        <p class="text-slate-600 text-sm mt-2 italic">"My mission is to listen to our partners and customers, turning their needs into a seamless sales journey and a better product."</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- CTA Section -->
        <section id="contact-us" class="bg-sky-600 py-20 text-center text-white">
            <div class="container mx-auto px-6">
                <h2 class="text-3xl md:text-5xl font-bold mb-4">Ready to Partner with Us?</h2>
                <p class="text-lg md:text-xl max-w-3xl mx-auto mb-8">
                    Join us and be part of this pool cleaning revolution. We look forward to building a long-lasting partnership and creating a new chapter of success together.
                </p>
                <a href="mailto:brandon@fairland.com.cn" class="bg-white text-sky-600 font-bold py-4 px-10 rounded-full shadow-lg transition-transform hover:scale-105 inline-block">Contact Us</a>
            </div>
        </section>

        <footer class="bg-slate-900 text-white py-12">
            <div class="container mx-auto px-6 text-center">
                <h3 class="text-3xl font-bold mb-4">Our Vision: One Pool, One Wireless Robot.</h3>
                <p class="max-w-2xl mx-auto mb-6">We believe the future of pool maintenance is effortless. With Fairland's 26 years of expertise, our steadfast commitment to partners, and the exceptional iGarden product, we are poised to lead the market and deliver extraordinary value to customers.</p>
                <p class="text-slate-400">&copy; 2025 Fairland & iGarden. All Rights Reserved.</p>
            </div>
        </footer>

        <script>
            document.addEventListener('DOMContentLoaded', function () {
                const mobileMenuButton = document.getElementById('mobile-menu-button');
                const mobileMenu = document.getElementById('mobile-menu');

                mobileMenuButton.addEventListener('click', () => {
                    mobileMenu.classList.toggle('hidden');
                });

                const navLinks = document.querySelectorAll('.nav-link');
                const sections = document.querySelectorAll('main section');

                const observerOptions = {
                    root: null,
                    rootMargin: '0px',
                    threshold: 0.5
                };

                const sectionObserver = new IntersectionObserver((entries, observer) => {
                    entries.forEach(entry => {
                        if (entry.isIntersecting) {
                            const id = entry.target.getAttribute('id');
                            navLinks.forEach(link => {
                                link.classList.remove('active');
                                if (link.getAttribute('href') === `#${id}`) {
                                    link.classList.add('active');
                                }
                            });
                        }
                    });
                }, observerOptions);

                sections.forEach(section => {
                    sectionObserver.observe(section);
                });

                const fadeElements = document.querySelectorAll('.fade-in');
                const fadeObserver = new IntersectionObserver((entries) => {
                    entries.forEach(entry => {
                        if (entry.isIntersecting) {
                            entry.target.classList.add('visible');
                        }
                    });
                }, { threshold: 0.1 });

                fadeElements.forEach(el => {
                    fadeObserver.observe(el);
                });

                const createChart = (ctx, type, data, options) => {
                     new Chart(ctx, { type, data, options });
                };

                const chartOptions = {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            position: 'bottom',
                            labels: {
                                color: '#64748B',
                                font: {
                                    family: "'Inter', sans-serif",
                                }
                            }
                        },
                        tooltip: {
                            bodyFont: {
                                family: "'Inter', sans-serif",
                            },
                            titleFont: {
                                family: "'Inter', sans-serif",
                            }
                        }
                    },
                    scales: {
                        y: {
                            ticks: { color: '#64748B' },
                            grid: { color: '#CBD5E1' }
                        },
                        x: {
                            ticks: { color: '#64748B' },
                            grid: { display: false }
                        }
                    }
                };

                const initCharts = () => {
                    const marketCtx = document.getElementById('marketPenetrationChart')?.getContext('2d');
                    if (marketCtx) {
                        createChart(marketCtx, 'doughnut', {
                            labels: ['Untapped Market (77%)', 'Existing Robot Users (23%)'],
                            datasets: [{
                                data: [77, 23],
                                backgroundColor: ['#3B82F6', '#94A3B8'],
                                borderColor: ['#F1F5F9'],
                                borderWidth: 4
                            }]
                        }, {
                            responsive: true,
                            maintainAspectRatio: false,
                            plugins: {
                                legend: { position: 'bottom', labels: { color: '#64748B' } },
                                tooltip: {
                                    callbacks: {
                                        label: (context) => `${context.label}: ${context.raw}%`
                                    }
                                }
                            }
                        });
                    }
                    
                    const usMarketCtx = document.getElementById('usMarketChart')?.getContext('2d');
                    if(usMarketCtx) {
                        createChart(usMarketCtx, 'line', {
                            labels: ['2022', '2023', '2024', '2025 (Est.)', '2026 (Proj.)'],
                            datasets: [
                                {
                                    label: 'US Pool Cleaner Penetration',
                                    data: [35, 40, 45, 50, 55],
                                    borderColor: '#3B82F6',
                                    backgroundColor: 'rgba(59, 130, 246, 0.2)',
                                    fill: true,
                                    tension: 0.4,
                                    pointBackgroundColor: '#3B82F6',
                                    pointBorderColor: '#fff',
                                    pointHoverBackgroundColor: '#fff',
                                    pointHoverBorderColor: '#3B82F6',
                                },
                                {
                                    label: 'Global Pool Cleaner Penetration',
                                    data: [20, 23, 26, 29, 32],
                                    borderColor: '#94A3B8',
                                    backgroundColor: 'rgba(148, 163, 184, 0.2)',
                                    fill: true,
                                    tension: 0.4,
                                    pointBackgroundColor: '#94A3B8',
                                    pointBorderColor: '#fff',
                                    pointHoverBackgroundColor: '#fff',
                                    pointHoverBorderColor: '#94A3B8',
                                }
                            ]
                        }, {
                            ...chartOptions,
                            scales: {
                                y: {
                                    beginAtZero: true,
                                    max: 100,
                                    ticks: {
                                        callback: function(value) {
                                            return value + '%'
                                        }
                                    },
                                },
                                x: {
                                    grid: { display: false }
                                }
                            },
                            plugins: {
                                legend: {
                                    position: 'top',
                                    labels: {
                                        color: '#64748B',
                                        font: {
                                            family: "'Inter', sans-serif"
                                        }
                                    }
                                }
                            },
                            animation: {
                                duration: 1500,
                                easing: 'easeInOutQuart'
                            }
                        });
                    }

                    const methodsCtx = document.getElementById('cleaningMethodsChart')?.getContext('2d');
                    if (methodsCtx) {
                        createChart(methodsCtx, 'bar', {
                            labels: ['Manual', 'Suction', 'Robotic', 'Pressure', 'Service Company'],
                            datasets: [{
                                label: 'Usage Percentage',
                                data: [33, 26, 23, 7, 11],
                                backgroundColor: '#3B82F6',
                                borderRadius: 4
                            }]
                        }, { ...chartOptions, indexAxis: 'y' });
                    }

                    const enduranceCtx = document.getElementById('enduranceChart')?.getContext('2d');
                    if (enduranceCtx) {
                        createChart(enduranceCtx, 'bar', {
                            labels: ['Industry Average', 'iGarden'],
                            datasets: [{
                                data: [2, 9],
                                backgroundColor: ['#94A3B8', '#3B82F6'],
                                borderRadius: 4
                            }]
                        }, {
                            ...chartOptions,
                            indexAxis: 'y',
                            scales: {
                                x: {
                                    ticks: {
                                        callback: function(value) {
                                            return value + 'h'
                                        }
                                    }
                                }
                            },
                            animation: {
                                duration: 1500,
                                easing: 'easeInOutQuart'
                            }
                        });
                    }
                };

                let chartsInitialized = false;
                const chartObserver = new IntersectionObserver((entries) => {
                    entries.forEach(entry => {
                        if (entry.isIntersecting && !chartsInitialized) {
                            initCharts();
                            chartsInitialized = true;
                            chartObserver.disconnect();
                        }
                    });
                }, { threshold: 0.1 });

                const firstChart = document.getElementById('marketPenetrationChart');
                if(firstChart) {
                    chartObserver.observe(firstChart);
                }

                const pathContainer = document.getElementById('path-animation-container');
                const coverageCounter = document.getElementById('coverage-counter');
                if (pathContainer && coverageCounter) {
                    const dot = pathContainer.querySelector('.path-dot');
                    let coverage = 0;
                    let isAnimating = false;

                    const animatePath = () => {
                        if(isAnimating) return;
                        isAnimating = true;
                        const width = pathContainer.clientWidth - 12;
                        const height = pathContainer.clientHeight - 12;
                        let x = 0;
                        let y = 10;
                        let direction = 1;
                        coverage = 0;

                        const move = () => {
                            if (coverage >= 100) {
                                coverage = 100;
                                coverageCounter.textContent = `Coverage: ${coverage}%`;
                                setTimeout(() => {
                                    coverage = 0;
                                    isAnimating = false;
                                    coverageCounter.textContent = `Coverage: 0%`;
                                }, 1000);
                                return;
                            }

                            x += 2 * direction;
                            dot.style.transform = `translate(${x}px, ${y}px)`;

                            if (x >= width || x <= 0) {
                                direction *= -1;
                                y += 30;
                            }

                            const totalPath = (height / 30) * width;
                            const currentPath = (y / 30) * width + x;
                            coverage = Math.min(100, Math.floor((currentPath / totalPath) * 100));

                            coverageCounter.textContent = `Coverage: ${coverage}%`;

                            if (y > height) {
                                y = 10;
                                x = 0;
                                direction = 1;
                            }
                            requestAnimationFrame(move);
                        };
                        move();
                    };

                    const pathObserver = new IntersectionObserver((entries) => {
                        entries.forEach(entry => {
                            if (entry.isIntersecting) {
                                animatePath();
                                pathObserver.disconnect();
                            }
                        });
                    }, { threshold: 0.5 });
                    pathObserver.observe(pathContainer);
                }
            });
        </script>
</body>
</html>
