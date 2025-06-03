<!DOCTYPE html>
<html lang="ko" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>STU Investment Partners LLC</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;500;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Noto Sans KR', sans-serif;
            background-color: #F8F9FA;
            color: #212529;
        }
        .hero-bg {
            background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://placehold.co/1920x1080/2D3748/FFFFFF?text=Global+Business');
            background-size: cover;
            background-position: center;
        }
        .nav-link {
            transition: color 0.3s;
        }
        .nav-link:hover {
            color: #3B82F6;
        }
        .section-title::after {
            content: '';
            display: block;
            width: 60px;
            height: 4px;
            background-color: #3B82F6;
            margin: 16px auto 0;
            border-radius: 2px;
        }
        .team-card {
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .team-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1);
        }
        .modal-overlay {
            transition: opacity 0.3s ease-in-out;
        }
        .modal-content {
            transition: transform 0.3s ease-in-out;
        }
        .portfolio-btn.active {
            background-color: #3B82F6;
            color: white;
        }
        .portfolio-item {
            transition: transform 0.3s, opacity 0.3s;
        }
        .tab-btn.active {
            border-bottom-color: #3B82F6;
            color: #3B82F6;
            font-weight: 700;
        }
    </style>
</head>
<body class="antialiased">

    <header id="header" class="bg-white/80 backdrop-blur-md shadow-md fixed w-full top-0 z-50 transition-all duration-300">
        <div class="container mx-auto px-6 py-3 flex justify-between items-center">
            <a href="#home" class="text-xl font-bold text-gray-800">STU Investment Partners</a>
            <nav class="hidden md:flex space-x-8">
                <a href="#about" class="nav-link text-gray-600">회사 소개</a>
                <a href="#team" class="nav-link text-gray-600">팀</a>
                <a href="#investment" class="nav-link text-gray-600">투자 철학</a>
                <a href="#portfolio" class="nav-link text-gray-600">포트폴리오</a>
                <a href="#news" class="nav-link text-gray-600">뉴스 & 인사이트</a>
                <a href="#contact" class="nav-link text-gray-600">연락처</a>
            </nav>
            <div class="md:hidden">
                <button id="mobile-menu-button" class="text-gray-800 focus:outline-none">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path></svg>
                </button>
            </div>
        </div>
        <div id="mobile-menu" class="hidden md:hidden">
            <a href="#about" class="block py-2 px-6 text-sm text-gray-700 hover:bg-gray-100">회사 소개</a>
            <a href="#team" class="block py-2 px-6 text-sm text-gray-700 hover:bg-gray-100">팀</a>
            <a href="#investment" class="block py-2 px-6 text-sm text-gray-700 hover:bg-gray-100">투자 철학</a>
            <a href="#portfolio" class="block py-2 px-6 text-sm text-gray-700 hover:bg-gray-100">포트폴리오</a>
            <a href="#news" class="block py-2 px-6 text-sm text-gray-700 hover:bg-gray-100">뉴스 & 인사이트</a>
            <a href="#contact" class="block py-2 px-6 text-sm text-gray-700 hover:bg-gray-100">연락처</a>
        </div>
    </header>

    <main>
        <section id="home" class="hero-bg h-screen flex items-center justify-center text-white text-center px-4">
            <div>
                <h1 class="text-4xl md:text-6xl font-bold mb-4 leading-tight animate-fade-in-down">미래를 조각하는 투자, <br class="md:hidden"/>STU Investment Partners가 함께합니다.</h1>
                <p class="text-lg md:text-xl max-w-3xl mx-auto mb-8 animate-fade-in-up">수십 년의 경험을 갖춘 전문가 팀이 귀사의 잠재력을 발굴하고, 글로벌 성공을 위한 맞춤형 지원을 제공합니다.</p>
                <div class="space-x-4">
                    <a href="#investment" class="bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 px-8 rounded-full transition duration-300">STU의 투자 이야기</a>
                    <a href="#team" class="bg-transparent border-2 border-white hover:bg-white hover:text-blue-600 text-white font-bold py-3 px-8 rounded-full transition duration-300">전문가 팀 살펴보기</a>
                </div>
            </div>
        </section>

        <section id="about" class="py-20 bg-white">
            <div class="container mx-auto px-6 text-center">
                <h2 class="section-title text-3xl font-bold text-gray-800 mb-12">Why STU?</h2>
                <p class="max-w-3xl mx-auto text-gray-600 mb-16">
                    STU Investment Partners LLC는 단순한 자금 공급자를 넘어, 기업가와 함께 호흡하며 지속 가능한 성장을 만들어가는 전략적 파트너입니다. 우리의 깊이 있는 통찰력과 광범위한 네트워크는 귀사의 성공적인 미래를 앞당길 것입니다.
                </p>
                <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-12">
                    <div class="p-8">
                        <div class="text-4xl text-blue-600 mb-4">👑</div>
                        <h3 class="text-xl font-bold mb-2">노련한 리더십</h3>
                        <p class="text-gray-600">김경배 CEO와 정성익 CIO의 도합 60년 경력이 이끄는 깊이 있는 전문성.</p>
                    </div>
                    <div class="p-8">
                        <div class="text-4xl text-blue-600 mb-4">🤝</div>
                        <h3 class="text-xl font-bold mb-2">산업과 투자의 융합</h3>
                        <p class="text-gray-600">석동호 본부장의 창업, 액셀러레이팅 경험과 투자 전문성의 결합.</p>
                    </div>
                    <div class="p-8">
                        <div class="text-4xl text-blue-600 mb-4">🌍</div>
                        <h3 class="text-xl font-bold mb-2">글로벌 네트워크</h3>
                        <p class="text-gray-600">John Lee의 미국, 중동을 아우르는 글로벌 투자 및 자금 조달 역량.</p>
                    </div>
                    <div class="p-8">
                        <div class="text-4xl text-blue-600 mb-4">📈</div>
                        <h3 class="text-xl font-bold mb-2">맞춤형 성장 지원</h3>
                        <p class="text-gray-600">기업의 단계와 필요에 맞춘 실질적인 가치 창출을 지원합니다.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="team" class="py-20">
            <div class="container mx-auto px-6 text-center">
                <h2 class="section-title text-3xl font-bold text-gray-800 mb-6">우리의 전문가들</h2>
                <p class="max-w-3xl mx-auto text-gray-600 mb-16">
                    STU Investment Partners의 가장 큰 자산은 사람입니다. 각 분야에서 최고의 전문성과 풍부한 경험을 갖춘 우리 팀은 기업의 성공적인 성장을 위한 든든한 지원군입니다.
                </p>
                <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-10">
                    <div class="team-card bg-white rounded-lg shadow-lg overflow-hidden cursor-pointer" onclick="openModal('kb-kim')">
                        <img src="https://placehold.co/400x400/E2E8F0/4A5568?text=K.B.Kim" alt="김경배 CEO" class="w-full h-64 object-cover">
                        <div class="p-6">
                            <h3 class="text-xl font-bold">김경배</h3>
                            <p class="text-blue-600">CEO & Managing Partner</p>
                            <p class="mt-2 text-sm text-gray-600">"30년 벤처투자 외길, 시장을 꿰뚫는 통찰력."</p>
                        </div>
                    </div>
                    <div class="team-card bg-white rounded-lg shadow-lg overflow-hidden cursor-pointer" onclick="openModal('si-jung')">
                        <img src="https://placehold.co/400x400/E2E8F0/4A5568?text=S.I.Jung" alt="정성익 CIO" class="w-full h-64 object-cover">
                        <div class="p-6">
                            <h3 class="text-xl font-bold">정성익</h3>
                            <p class="text-blue-600">CIO & Partner</p>
                            <p class="mt-2 text-sm text-gray-600">"산업은행 30년, 기업금융과 투자 분석의 베테랑."</p>
                        </div>
                    </div>
                    <div class="team-card bg-white rounded-lg shadow-lg overflow-hidden cursor-pointer" onclick="openModal('dh-seok')">
                        <img src="https://placehold.co/400x400/E2E8F0/4A5568?text=D.H.Seok" alt="석동호 투자본부장" class="w-full h-64 object-cover">
                        <div class="p-6">
                            <h3 class="text-xl font-bold">석동호</h3>
                            <p class="text-blue-600">전무, 투자본부장</p>
                            <p class="mt-2 text-sm text-gray-600">"창업부터 투자까지, 산업 현장과 자본 시장의 연결."</p>
                        </div>
                    </div>
                    <div class="team-card bg-white rounded-lg shadow-lg overflow-hidden cursor-pointer" onclick="openModal('j-lee')">
                        <img src="https://placehold.co/400x400/E2E8F0/4A5568?text=J.Lee" alt="John Lee 글로벌 투자 담당" class="w-full h-64 object-cover">
                        <div class="p-6">
                            <h3 class="text-xl font-bold">John Lee</h3>
                            <p class="text-blue-600">이사, 글로벌 투자/파이낸싱</p>
                            <p class="mt-2 text-sm text-gray-600">"국경을 넘나드는 파이낸싱, 글로벌 성공의 키."</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <section id="investment" class="py-20 bg-white">
            <div class="container mx-auto px-6">
                <h2 class="section-title text-3xl font-bold text-gray-800 mb-16 text-center">우리의 투자 접근법</h2>
                <div class="max-w-4xl mx-auto">
                    <div class="border-b border-gray-200 mb-8">
                        <nav class="-mb-px flex space-x-8" aria-label="Tabs">
                            <button class="tab-btn active whitespace-nowrap py-4 px-1 border-b-2 font-medium text-lg" data-tab="philosophy">투자 철학</button>
                            <button class="tab-btn whitespace-nowrap py-4 px-1 border-b-2 font-medium text-lg text-gray-500" data-tab="focus">투자 분야</button>
                            <button class="tab-btn whitespace-nowrap py-4 px-1 border-b-2 font-medium text-lg text-gray-500" data-tab="value-add">가치 창출</button>
                        </nav>
                    </div>
                    <div id="philosophy-content" class="tab-content">
                        <ul class="space-y-6">
                            <li class="flex items-start"><span class="text-blue-600 mr-4 mt-1">✔</span><div><h4 class="font-bold text-lg">사람 중심 (People-First)</h4><p class="text-gray-600">뛰어난 창업가와 팀의 역량에 최우선 가치를 둡니다.</p></div></li>
                            <li class="flex items-start"><span class="text-blue-600 mr-4 mt-1">✔</span><div><h4 class="font-bold text-lg">기본에 충실 (Fundamentals-Driven)</h4><p class="text-gray-600">지속 가능한 비즈니스 모델과 명확한 시장 기회에 집중합니다.</p></div></li>
                            <li class="flex items-start"><span class="text-blue-600 mr-4 mt-1">✔</span><div><h4 class="font-bold text-lg">장기적 관점 (Long-Term Horizon)</h4><p class="text-gray-600">단기적 성과보다는 장기적인 기업 가치 증대를 목표로 합니다.</p></div></li>
                            <li class="flex items-start"><span class="text-blue-600 mr-4 mt-1">✔</span><div><h4 class="font-bold text-lg">적극적 지원 (Active Support)</h4><p class="text-gray-600">단순 자금 투자를 넘어 경영, 전략, 네트워크 등 다방면으로 지원합니다.</p></div></li>
                            <li class="flex items-start"><span class="text-blue-600 mr-4 mt-1">✔</span><div><h4 class="font-bold text-lg">글로벌 지향 (Global Perspective)</h4><p class="text-gray-600">국내 시장을 넘어 글로벌 시장에서의 성공 가능성을 중요하게 평가합니다.</p></div></li>
                        </ul>
                    </div>
                    <div id="focus-content" class="tab-content hidden">
                        <p class="text-gray-600 mb-6">미래 성장 가능성이 높은 핵심 산업 분야의 혁신 기업을 발굴하여 집중적으로 투자합니다. </p>
                        <div class="grid md:grid-cols-2 gap-x-8 gap-y-4">
                            <span class="p-2 font-medium">🤖 AI & 머신러닝</span>
                            <span class="p-2 font-medium">☁️ SaaS & 클라우드</span>
                            <span class="p-2 font-medium">❤️ 바이오 & 헬스케어</span>
                            <span class="p-2 font-medium">💳 핀테크</span>
                            <span class="p-2 font-medium">🚗 모빌리티</span>
                            <span class="p-2 font-medium">🔬 딥테크</span>
                            <span class="p-2 font-medium">🌱 ESG & 임팩트</span>
                            <span class="p-2 font-medium">🚀 성장 단계 (Growth Stage)</span>
                        </div>
                    </div>
                    <div id="value-add-content" class="tab-content hidden">
                        <p class="text-gray-600 mb-6">STU는 단순한 자금 투자를 넘어, 포트폴리오 기업의 성장을 위해 다각도로 지원하는 전략적 파트너입니다.</p>
                        <ul class="list-disc list-inside space-y-3 text-gray-700">
                            <li><span class="font-bold">전략적 자문:</span> 경영, 사업 개발, 시장 진입 전략 등</li>
                            <li><span class="font-bold">네트워킹:</span> 산업 전문가, 잠재 고객/파트너, 후속 투자자 연결</li>
                            <li><span class="font-bold">글로벌 확장 지원:</span> 해외 시장 정보 제공, 진출 전략 수립, 현지 파트너 연결</li>
                            <li><span class="font-bold">인재 영입 지원:</span> 핵심 인력 확보를 위한 자문 및 추천</li>
                            <li><span class="font-bold">후속 투자 유치 지원:</span> 성장을 위한 추가 자금 조달 지원</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <section id="portfolio" class="py-20">
            <div class="container mx-auto px-6 text-center">
                <h2 class="section-title text-3xl font-bold text-gray-800 mb-6">포트폴리오</h2>
                <p class="max-w-3xl mx-auto text-gray-600 mb-12">
                    STU Investment Partners가 함께 성장하고 있는 혁신적인 기업들을 소개합니다. 이들은 각자의 분야에서 미래를 만들어가고 있습니다.
                </p>
                <div class="flex justify-center flex-wrap gap-2 mb-12">
                    <button class="portfolio-btn active py-2 px-4 rounded-full bg-gray-200 text-gray-700 transition" data-filter="all">All</button>
                    <button class="portfolio-btn py-2 px-4 rounded-full bg-gray-200 text-gray-700 transition" data-filter="ai">AI</button>
                    <button class="portfolio-btn py-2 px-4 rounded-full bg-gray-200 text-gray-700 transition" data-filter="healthcare">Healthcare</button>
                    <button class="portfolio-btn py-2 px-4 rounded-full bg-gray-200 text-gray-700 transition" data-filter="saas">SaaS</button>
                    <button class="portfolio-btn py-2 px-4 rounded-full bg-gray-200 text-gray-700 transition" data-filter="fintech">Fintech</button>
                </div>
                <div id="portfolio-grid" class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-8">
                    <div class="portfolio-item p-4 bg-white rounded-lg flex items-center justify-center h-24 shadow-md" data-category="ai">
                        <img src="https://placehold.co/150x60/cccccc/333333?text=AI+Innovation" alt="AI Innovation">
                    </div>
                    <div class="portfolio-item p-4 bg-white rounded-lg flex items-center justify-center h-24 shadow-md" data-category="healthcare">
                        <img src="https://placehold.co/150x60/cccccc/333333?text=Medical" alt="Medical">
                    </div>
                    <div class="portfolio-item p-4 bg-white rounded-lg flex items-center justify-center h-24 shadow-md" data-category="saas">
                        <img src="https://placehold.co/150x60/cccccc/333333?text=CloudF" alt="CloudF">
                    </div>
                    <div class="portfolio-item p-4 bg-white rounded-lg flex items-center justify-center h-24 shadow-md" data-category="fintech">
                        <img src="https://placehold.co/150x60/cccccc/333333?text=Payment" alt="Payment">
                    </div>
                    <div class="portfolio-item p-4 bg-white rounded-lg flex items-center justify-center h-24 shadow-md" data-category="ai">
                        <img src="https://placehold.co/150x60/cccccc/333333?text=DeepTech" alt="DeepTech">
                    </div>
                    <div class="portfolio-item p-4 bg-white rounded-lg flex items-center justify-center h-24 shadow-md" data-category="healthcare">
                        <img src="https://placehold.co/150x60/cccccc/333333?text=Bio_Healthcare" alt="Bio_Healthcare">
                    </div>
                     <div class="portfolio-item p-4 bg-white rounded-lg flex items-center justify-center h-24 shadow-md" data-category="saas">
                        <img src="https://placehold.co/150x60/cccccc/333333?text=WorkEasy" alt="WorkEasy">
                    </div>
                    <div class="portfolio-item p-4 bg-white rounded-lg flex items-center justify-center h-24 shadow-md" data-category="fintech">
                        <img src="https://placehold.co/150x60/cccccc/333333?text=Blockchain" alt="Blcokchain">
                    </div>
                     <div class="portfolio-item p-4 bg-white rounded-lg flex items-center justify-center h-24 shadow-md" data-category="ai">
                        <img src="https://placehold.co/150x60/cccccc/333333?text=AI" alt="AI">
                    </div>
                    <div class="portfolio-item p-4 bg-white rounded-lg flex items-center justify-center h-24 shadow-md" data-category="healthcare">
                        <img src="https://placehold.co/150x60/cccccc/333333?text=Care" alt="Care">
                    </div>
                </div>                    <div class="portfolio-item p-4 bg-white rounded-lg flex items-center justify-center h-24 shadow-md" data-category="fintech">
                        <img src="https://placehold.co/150x60/cccccc/333333?text=STO/RWA" alt="STO/RWA">
            </div>
        </section>

        <section id="news" class="py-20 bg-white">
            <div class="container mx-auto px-6">
                <h2 class="section-title text-3xl font-bold text-gray-800 mb-16 text-center">뉴스 & 인사이트</h2>
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <div class="bg-white rounded-lg shadow-md overflow-hidden">
                        <img src="https://placehold.co/600x400/A0AEC0/FFFFFF?text=Insight" class="w-full h-48 object-cover">
                        <div class="p-6">
                            <span class="text-sm text-gray-500">Market Insights</span>
                            <h3 class="font-bold text-lg my-2">격변기 벤처 투자 시장의 기회</h3>
                            <p class="text-gray-600 text-sm mb-4">김경배 CEO가 말하는 현재 시장의 위기와 기회...</p>
                            <a href="#" class="text-blue-600 font-semibold">더 읽기 &rarr;</a>
                        </div>
                    </div>
                    <div class="bg-white rounded-lg shadow-md overflow-hidden">
                        <img src="https://placehold.co/600x400/718096/FFFFFF?text=News" class="w-full h-48 object-cover">
                        <div class="p-6">
                            <span class="text-sm text-gray-500">STU News</span>
                            <h3 class="font-bold text-lg my-2">STU, 헬스케어 스타트업 'MediTech'에 투자</h3>
                            <p class="text-gray-600 text-sm mb-4">STU가 혁신적인 디지털 헬스케어 기업인 MediTech에...</p>
                            <a href="#" class="text-blue-600 font-semibold">더 읽기 &rarr;</a>
                        </div>
                    </div>
                    <div class="bg-white rounded-lg shadow-md overflow-hidden">
                        <img src="https://placehold.co/600x400/4A5568/FFFFFF?text=Global" class="w-full h-48 object-cover">
                        <div class="p-6">
                            <span class="text-sm text-gray-500">Global Trend</span>
                            <h3 class="font-bold text-lg my-2">아시아 시장 진출을 위한 성공 방정식</h3>
                            <p class="text-gray-600 text-sm mb-4">John Lee 이사가 분석하는 아시아 시장의 최신 트렌드...</p>
                            <a href="#" class="text-blue-600 font-semibold">더 읽기 &rarr;</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact" class="py-20">
            <div class="container mx-auto px-6">
                <h2 class="section-title text-3xl font-bold text-gray-800 mb-16 text-center">연락처</h2>
                <div class="max-w-4xl mx-auto bg-white p-8 md:p-12 rounded-lg shadow-lg grid md:grid-cols-2 gap-12">
                    <div>
                        <h3 class="text-2xl font-bold mb-4">투자 제안 (Pitch Us)</h3>
                        <p class="text-gray-600 mb-6">혁신적인 아이디어와 세상을 바꿀 열정을 가진 창업가들을 기다립니다. 아래 이메일로 사업계획서를 보내주세요.</p>
                        <a href="mailto:pitch@stu-invest.com" class="font-semibold text-blue-600">dongh.seok@gmail.com</a>
                        
                        <h3 class="text-2xl font-bold mt-10 mb-4">일반 문의</h3>
                        <p class="text-gray-600 mb-2">서울특별시 강남구 테헤란로 431, #4003, Justco타워</p>
                        <p class="text-gray-600">Tel: 010-8234-5955</p>
                    </div>
                    <form>
                        <div class="mb-4">
                            <label for="name" class="block text-gray-700 font-bold mb-2">이름</label>
                            <input type="text" id="name" name="name" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500">
                        </div>
                        <div class="mb-4">
                            <label for="email" class="block text-gray-700 font-bold mb-2">이메일</p>
                            <input type="email" id="email" name="email" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500">
                        </div>
                        <div class="mb-4">
                            <label for="message" class="block text-gray-700 font-bold mb-2">메시지</label>
                            <textarea id="message" name="message" rows="4" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"></textarea>
                        </div>
                        <button type="submit" class="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 px-4 rounded-lg transition duration-300">메시지 보내기</button>
                    </form>
                </div>
            </div>
        </section>
    </main>

    <footer class="bg-gray-800 text-white py-8">
        <div class="container mx-auto px-6 text-center">
            <p>&copy; 2024 STU Investment Partners LLC. All Rights Reserved.</p>
        </div>
    </footer>
    
    <div id="modal-container" class="hidden"></div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const mobileMenuButton = document.getElementById('mobile-menu-button');
            const mobileMenu = document.getElementById('mobile-menu');

            mobileMenuButton.addEventListener('click', () => {
                mobileMenu.classList.toggle('hidden');
            });
            
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    if(this.getAttribute('href') !== '#') {
                         document.querySelector(this.getAttribute('href')).scrollIntoView({
                            behavior: 'smooth'
                        });
                    }
                    if(mobileMenu.classList.contains('hidden') === false) {
                        mobileMenu.classList.add('hidden');
                    }
                });
            });

            const header = document.getElementById('header');
            window.addEventListener('scroll', () => {
                if (window.scrollY > 50) {
                    header.classList.add('py-2');
                    header.classList.remove('py-3');
                } else {
                    header.classList.add('py-3');
                    header.classList.remove('py-2');
                }
            });

            const portfolioBtns = document.querySelectorAll('.portfolio-btn');
            const portfolioItems = document.querySelectorAll('.portfolio-item');

            portfolioBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    portfolioBtns.forEach(b => b.classList.remove('active'));
                    btn.classList.add('active');

                    const filter = btn.getAttribute('data-filter');

                    portfolioItems.forEach(item => {
                        item.style.transform = 'scale(0)';
                        item.style.opacity = '0';
                        setTimeout(() => {
                           if (filter === 'all' || item.getAttribute('data-category') === filter) {
                                item.classList.remove('hidden');
                                setTimeout(() => {
                                    item.style.transform = 'scale(1)';
                                    item.style.opacity = '1';
                                }, 50);
                            } else {
                                item.classList.add('hidden');
                            }
                        }, 300);
                    });
                });
            });
            
            const tabBtns = document.querySelectorAll('.tab-btn');
            const tabContents = document.querySelectorAll('.tab-content');
            
            tabBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    tabBtns.forEach(b => b.classList.remove('active'));
                    btn.classList.add('active');
                    
                    const tabId = btn.getAttribute('data-tab');
                    
                    tabContents.forEach(content => {
                        if(content.id === `${tabId}-content`) {
                            content.classList.remove('hidden');
                        } else {
                            content.classList.add('hidden');
                        }
                    });
                });
            });

        });

        const teamData = {
            'kb-kim': {
                name: '김경배 (Kyung-Bae Kim)',
                title: 'CEO & Managing Partner',
                image: 'https://placehold.co/400x400/E2E8F0/4A5568?text=K.B.Kim',
                description: "30년 이상의 벤처투자 경력을 보유한 베테랑으로, PWC, SL인베스트먼트를 거쳐 포이보스창업투자회사 CEO를 역임하며 수많은 유망 기업을 발굴하고 성공적인 투자 회수를 이끌었습니다. 시장의 흐름을 읽는 날카로운 통찰력과 기업의 본질을 꿰뚫는 안목으로 STU의 투자를 총괄합니다.",
                career: ['PWC 컨설팅 (경영 컨설턴트)', 'SL인베스트먼트 (파트너, 수석 팀장)', '포이보스창업투자회사 (대표이사/CEO)'],
                expertise: ['ICT', '플랫폼', '소비재', 'M&A', 'IPO 전략'],
                message: "위대한 기업은 위대한 기업가로부터 시작됩니다. STU는 기업가의 꿈을 현실로 만드는 여정에 가장 신뢰할 수 있는 파트너가 될 것입니다."
            },
            'si-jung': {
                name: '정성익 (Sung-Ik Jung)',
                title: 'CIO & Partner',
                image: 'https://placehold.co/400x400/E2E8F0/4A5568?text=S.I.Jung',
                description: "한국산업은행에서 30년간 재직하며 기업금융, 투자 심사, 리스크 관리 등 금융 전반에 걸쳐 깊이 있는 경험과 전문성을 쌓았습니다. 거시 경제 분석과 산업 동향 예측을 바탕으로 안정적이면서도 성장 잠재력이 높은 투자 포트폴리오를 구축하는 데 핵심적인 역할을 수행합니다.",
                career: ['한국산업은행 (기업금융 부문 팀장, 투자 심사역, 리스크 관리 총괄 등)'],
                expertise: ['기업금융', '투자 분석', '리스크 관리', '금융 구조화', '산업 정책 분석'],
                message: "철저한 분석과 데이터 기반의 의사결정은 성공적인 투자의 기본입니다. 기업의 지속 가능한 성장을 위한 최적의 금융 솔루션을 제공하겠습니다."
            },
            'dh-seok': {
                name: '석동호 (Dong-Ho Seok)',
                title: '전무, 투자본부장',
                image: 'https://placehold.co/400x400/E2E8F0/4A5568?text=D.H.Seok',
                description: "액셀러레이터로서 다수의 초기 기업을 성공적으로 육성하고, 직접 헬스케어 기업을 창업하여 운영한 경험을 통해 산업 현장에 대한 깊은 이해를 갖추고 있습니다. 벤처캐피탈에서의 투자 경력을 더해, 기술 기반 기업의 성장 전략 수립과 실행에 탁월한 역량을 발휘합니다.",
                career: ['[특정 액셀러레이터 명칭] (파트너, 프로그램 총괄)', '[창업한 헬스케어 회사 명칭] (대표이사/CEO)', '[벤처캐피탈 명칭] (투자 심사역)'],
                expertise: ['초기 기업 투자 및 육성', '헬스케어', '바이오', '기술 사업화', '사업 개발 전략'],
                message: "창업가의 열정과 혁신적인 아이디어가 세상을 바꿀 수 있다고 믿습니다. 그 여정에 필요한 실질적인 지원과 통찰력을 제공하겠습니다."
            },
            'j-lee': {
                name: 'John Lee',
                title: '이사, 글로벌 투자/파이낸싱',
                image: 'https://placehold.co/400x400/E2E8F0/4A5568?text=J.Lee',
                description: "미국, 한국, 카타르 등 다양한 국가에서 글로벌 투자 및 파이낸싱 업무를 수행하며 폭넓은 국제 금융 네트워크와 경험을 축적했습니다. STU의 글로벌 투자 전략을 수립하고, 포트폴리오 기업의 해외 시장 진출 및 글로벌 자금 조달을 적극 지원합니다.",
                career: ['[미국 투자은행 명칭] (IB Division)', '[카타르 국부펀드 또는 투자기관 명칭] (Investment Manager)', '[한국 사모펀드 또는 투자사 명칭] (Cross-border Investment Team)'],
                expertise: ['글로벌 파이낸싱', '해외 직접 투자', '크로스보더 M&A', '국제 자본 시장', '펀드 조성'],
                message: "국경을 넘어선 기회를 포착하고, 한국의 혁신 기업들이 세계 무대에서 당당히 경쟁할 수 있도록 최선을 다해 지원하겠습니다."
            }
        };

        function openModal(teamMemberId) {
            const data = teamData[teamMemberId];
            if (!data) return;

            const modalHTML = `
                <div id="modal-overlay" class="modal-overlay fixed inset-0 bg-black bg-opacity-70 flex items-center justify-center p-4 z-50 opacity-0" onclick="closeModal()">
                    <div id="modal-content" class="modal-content bg-white rounded-lg shadow-2xl w-full max-w-4xl max-h-[90vh] overflow-y-auto transform scale-95" onclick="event.stopPropagation()">
                        <div class="p-6 md:p-8 relative">
                            <button onclick="closeModal()" class="absolute top-4 right-4 text-gray-400 hover:text-gray-600">&times;</button>
                            <div class="grid md:grid-cols-3 gap-8">
                                <div class="md:col-span-1">
                                    <img src="${data.image}" alt="${data.name}" class="rounded-lg w-full mb-4">
                                    <h2 class="text-2xl font-bold">${data.name}</h2>
                                    <p class="text-blue-600 font-semibold">${data.title}</p>
                                </div>
                                <div class="md:col-span-2">
                                    <p class="text-gray-700 mb-6">${data.description}</p>
                                    <div class="mb-6">
                                        <h4 class="font-bold text-lg mb-2 border-b pb-1">주요 경력</h4>
                                        <ul class="list-disc list-inside text-gray-600 space-y-1">
                                            ${data.career.map(c => `<li>${c}</li>`).join('')}
                                        </ul>
                                    </div>
                                    <div class="mb-6">
                                        <h4 class="font-bold text-lg mb-2 border-b pb-1">전문 분야</h4>
                                        <div class="flex flex-wrap gap-2">
                                           ${data.expertise.map(e => `<span class="bg-gray-200 text-gray-700 text-sm font-medium px-3 py-1 rounded-full">${e}</span>`).join('')}
                                        </div>
                                    </div>
                                    <div class="bg-gray-100 p-4 rounded-lg">
                                        <p class="text-gray-800 font-semibold italic">"${data.message}"</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            `;

            document.getElementById('modal-container').innerHTML = modalHTML;
            document.getElementById('modal-container').classList.remove('hidden');

            setTimeout(() => {
                document.getElementById('modal-overlay').classList.remove('opacity-0');
                document.getElementById('modal-content').classList.remove('scale-95');
            }, 10);
        }

        function closeModal() {
            const modalOverlay = document.getElementById('modal-overlay');
            const modalContent = document.getElementById('modal-content');
            if(modalOverlay && modalContent) {
                modalOverlay.classList.add('opacity-0');
                modalContent.classList.add('scale-95');

                setTimeout(() => {
                    document.getElementById('modal-container').classList.add('hidden');
                    document.getElementById('modal-container').innerHTML = '';
                }, 300);
            }
        }
    </script>
</body>
</html>
