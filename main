<html>
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>실버가드 (Silver Guard) - Smart City Solution</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <link href="https://cdn.jsdelivr.net/npm/remixicon@3.5.0/fonts/remixicon.css" rel="stylesheet">
    
    <style>
        @import url('https://cdn.jsdelivr.net/gh/orioncactus/pretendard/dist/web/static/pretendard.css');
        body { font-family: 'Pretendard', sans-serif; }
        
        .no-scrollbar::-webkit-scrollbar { display: none; }
        .no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
        
        @keyframes marquee {
            0% { transform: translateX(0); }
            100% { transform: translateX(-50%); }
        }
        .animate-marquee {
            animation: marquee 40s linear infinite;
        }
        .fade-in-up {
            animation: fadeInUp 0.8s ease-out forwards;
        }
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-900 overflow-x-hidden">
    <div id="root"></div>

    <script type="text/babel">
        const { useState, useEffect } = React;

        // --- COMPONENTS ---

        const Badge = ({ children, color = "blue" }) => {
            const colors = {
                blue: "bg-blue-100 text-blue-800 border-blue-200",
                green: "bg-green-100 text-green-800 border-green-200",
                red: "bg-red-100 text-red-800 border-red-200",
                orange: "bg-orange-100 text-orange-800 border-orange-200",
                gray: "bg-slate-100 text-slate-800 border-slate-200",
            };
            return (
                <span className={`px-2.5 py-0.5 rounded-full text-xs font-bold border ${colors[color]}`}>
                    {children}
                </span>
            );
        };

        const SectionTitle = ({ subtitle, title, description, align = "center" }) => (
            <div className={`mb-16 ${align === 'center' ? 'text-center' : 'text-left'} max-w-4xl mx-auto px-4`}>
                <span className="text-orange-600 font-bold tracking-widest text-sm uppercase mb-2 block">{subtitle}</span>
                <h2 className="text-3xl md:text-5xl font-bold mb-6 text-slate-900 leading-tight">{title}</h2>
                {description && <p className="text-lg text-slate-500 leading-relaxed">{description}</p>}
            </div>
        );

        const App = () => {
            const [scrolled, setScrolled] = useState(false);
            
            // Scroll Listener
            useEffect(() => {
                const handleScroll = () => setScrolled(window.scrollY > 50);
                window.addEventListener('scroll', handleScroll);
                return () => window.removeEventListener('scroll', handleScroll);
            }, []);

            // Data Simulation
            const [logs, setLogs] = useState([
                { id: 'SG-ROAD-0042', cat: '도로교통', item: '포트홀', loc: '관악구 신림동', status: '긴급', time: '방금 전' },
                { id: 'SG-ENV-0103', cat: '환경안전', item: '무단투기', loc: '동작구 사당동', status: '주의', time: '1분 전' },
                { id: 'SG-FAC-0892', cat: '시설물', item: '벤치파손', loc: '서초구 양재동', status: '관찰', time: '3분 전' },
                { id: 'SG-SAFE-1102', cat: '안전', item: '보도블록', loc: '강남구 역삼동', status: '완료', time: '5분 전' },
                { id: 'SG-ROAD-2201', cat: '도로교통', item: '볼라드파손', loc: '송파구 잠실동', status: '긴급', time: '8분 전' },
                { id: 'SG-ENV-3302', cat: '환경안전', item: '배수구막힘', loc: '마포구 서교동', status: '주의', time: '12분 전' },
            ]);

            return (
                <div className="min-h-screen flex flex-col font-sans">
                    
                    {/* NAV BAR */}
                    <nav className={`fixed top-0 w-full z-50 transition-all duration-300 ${scrolled ? 'bg-white/90 backdrop-blur-md shadow-sm py-4' : 'bg-transparent py-6'}`}>
                        <div className="container mx-auto px-6 flex justify-between items-center">
                            <div className="flex items-center gap-2">
                                <div className="w-8 h-8 bg-orange-600 rounded-lg flex items-center justify-center text-white font-bold text-lg">S</div>
                                <span className={`text-xl font-bold tracking-tight ${scrolled ? 'text-slate-900' : 'text-white'}`}>Silver Guard</span>
                            </div>
                            <div className="hidden md:flex gap-8 text-sm font-medium">
                                <a href="#problem" className={`hover:text-orange-500 transition ${scrolled ? 'text-slate-600' : 'text-slate-300'}`}>문제점</a>
                                <a href="#solution" className={`hover:text-orange-500 transition ${scrolled ? 'text-slate-600' : 'text-slate-300'}`}>솔루션</a>
                                <a href="#features" className={`hover:text-orange-500 transition ${scrolled ? 'text-slate-600' : 'text-slate-300'}`}>기술력</a>
                                <a href="#contact" className={`hover:text-orange-500 transition ${scrolled ? 'text-slate-600' : 'text-slate-300'}`}>도입 문의</a>
                            </div>
                            <button className="bg-orange-600 hover:bg-orange-700 text-white px-5 py-2 rounded-lg text-sm font-bold transition shadow-lg">문의하기</button>
                        </div>
                    </nav>

                    {/* 1. HERO SECTION */}
                    <header className="relative min-h-screen flex flex-col justify-center items-center bg-slate-900 text-white overflow-hidden pt-20">
                        {/* Dynamic Background */}
                        <div className="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1480714378408-67cf0d13bc1b?q=80&w=2070&auto=format&fit=crop')] bg-cover bg-center opacity-30"></div>
                        <div className="absolute inset-0 bg-gradient-to-t from-slate-900 via-slate-900/80 to-transparent"></div>
                        
                        <div className="relative z-10 container mx-auto px-4 text-center mt-[-5vh]">
                            <div className="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-slate-800/50 border border-slate-700 backdrop-blur-md mb-8 fade-in-up" style={{animationDelay: '0.1s'}}>
                                <span className="flex h-3 w-3 relative">
                                    <span className="animate-ping absolute inline-flex h-full w-full rounded-full bg-green-400 opacity-75"></span>
                                    <span className="relative inline-flex rounded-full h-3 w-3 bg-green-500"></span>
                                </span>
                                <span className="text-sm font-medium text-slate-300">System Operational: Seoul Metro Area</span>
                            </div>
                            
                            <h1 className="text-5xl md:text-7xl lg:text-8xl font-bold mb-8 leading-tight tracking-tight fade-in-up" style={{animationDelay: '0.3s'}}>
                                도시의 <span className="text-transparent bg-clip-text bg-gradient-to-r from-orange-400 to-red-500">사각지대</span>를<br/>
                                <span className="text-white">데이터 자산</span>으로.
                            </h1>
                            
                            <p className="text-xl md:text-2xl text-slate-400 mb-12 max-w-3xl mx-auto font-light fade-in-up" style={{animationDelay: '0.5s'}}>
                                실버가드는 도시의 유휴 인력인 '시니어'를 전문 데이터 요원으로 전환하여,<br class="hidden md:block"/>
                                가장 정밀하고 경제적인 <strong>스마트시티 데이터 네트워크</strong>를 구축합니다.
                            </p>
                            
                            <div className="flex flex-col sm:flex-row gap-4 justify-center fade-in-up" style={{animationDelay: '0.7s'}}>
                                <button className="bg-orange-600 hover:bg-orange-700 text-white px-8 py-4 rounded-xl text-lg font-bold transition flex items-center justify-center gap-2 shadow-[0_0_40px_-10px_rgba(234,88,12,0.5)]">
                                    도입 문의하기 <i className="ri-arrow-right-line"></i>
                                </button>
                                <button className="bg-white/10 hover:bg-white/20 backdrop-blur text-white border border-white/20 px-8 py-4 rounded-xl text-lg font-medium transition flex items-center justify-center gap-2">
                                    <i className="ri-download-line"></i> 서비스 소개서
                                </button>
                            </div>
                        </div>

                        {/* Scrolling Ticker */}
                        <div className="absolute bottom-0 w-full border-t border-white/10 bg-black/40 backdrop-blur-sm py-4">
                            <div className="flex gap-8 animate-marquee whitespace-nowrap">
                                {[...logs, ...logs, ...logs].map((log, i) => (
                                    <div key={i} className="flex items-center gap-3 text-sm text-slate-300 font-mono bg-slate-800/50 px-4 py-2 rounded border border-white/5">
                                        <span className={`w-2 h-2 rounded-full ${log.status === '긴급' ? 'bg-red-500 animate-pulse' : log.status === '주의' ? 'bg-yellow-500' : 'bg-green-500'}`}></span>
                                        <span className="text-white font-bold">{log.id}</span>
                                        <span className="opacity-50">|</span>
                                        <span>{log.cat}</span>
                                        <span className="text-orange-400">[{log.item}]</span>
                                        <span>{log.loc}</span>
                                        <span className="text-xs text-slate-500">{log.time}</span>
                                    </div>
                                ))}
                            </div>
                        </div>
                    </header>

                    {/* 2. STATS SECTION (Trust) */}
                    <section className="py-12 bg-white border-b border-slate-100">
                        <div className="container mx-auto px-6">
                            <div className="grid grid-cols-2 md:grid-cols-4 gap-8 divide-x divide-slate-100">
                                <div className="text-center">
                                    <p className="text-4xl font-bold text-slate-900 mb-2">1,000+</p>
                                    <p className="text-sm text-slate-500 uppercase tracking-wide">데이터 표준 코드</p>
                                </div>
                                <div className="text-center">
                                    <p className="text-4xl font-bold text-orange-600 mb-2">70%</p>
                                    <p className="text-sm text-slate-500 uppercase tracking-wide">지자체 예산 절감</p>
                                </div>
                                <div className="text-center">
                                    <p className="text-4xl font-bold text-slate-900 mb-2">24h</p>
                                    <p className="text-sm text-slate-500 uppercase tracking-wide">리포트 생성 시간</p>
                                </div>
                                <div className="text-center">
                                    <p className="text-4xl font-bold text-slate-900 mb-2">0원</p>
                                    <p className="text-sm text-slate-500 uppercase tracking-wide">센서 설치 비용</p>
                                </div>
                            </div>
                        </div>
                    </section>

                    {/* 3. PROBLEM & SOLUTION */}
                    <section id="problem" className="py-24 bg-slate-50">
                        <div className="container mx-auto px-6">
                            <SectionTitle 
                                subtitle="THE REALITY" 
                                title="스마트시티의 딜레마" 
                                description="우리는 첨단 기술의 시대에 살고 있지만, 여전히 도시는 구멍(Pothole)나 있고 예산은 부족합니다."
                            />
                            
                            <div className="grid md:grid-cols-3 gap-8">
                                {[
                                    { icon: "ri-eye-off-line", title: "데이터 사각지대", desc: "CCTV는 대로변만 봅니다. 골목길, 이면도로, 반지하의 위험은 누가 감지합니까?" },
                                    { icon: "ri-money-dollar-circle-line", title: "예산의 비효율", desc: "매년 수십억 원의 노인 일자리 예산, 단순 환경미화로 흘려보내시겠습니까?" },
                                    { icon: "ri-user-unfollow-line", title: "관리 인력 부족", desc: "공무원 1명이 담당하는 관할 구역은 여의도 면적의 10배. 전수 조사는 불가능합니다." }
                                ].map((item, i) => (
                                    <div key={i} className="bg-white p-10 rounded-3xl shadow-sm hover:shadow-xl transition duration-300 border border-slate-100 group">
                                        <div className="w-16 h-16 bg-slate-100 rounded-2xl flex items-center justify-center text-3xl text-slate-600 mb-6 group-hover:bg-orange-600 group-hover:text-white transition">
                                            <i className={item.icon}></i>
                                        </div>
                                        <h3 className="text-2xl font-bold mb-4 text-slate-900">{item.title}</h3>
                                        <p className="text-slate-600 leading-relaxed">{item.desc}</p>
                                    </div>
                                ))}
                            </div>
                        </div>
                    </section>

                    {/* 4. PROCESS */}
                    <section id="solution" className="py-24 bg-white relative overflow-hidden">
                        <div className="absolute top-0 right-0 w-1/2 h-full bg-slate-50 -skew-x-12 z-0 opacity-50"></div>
                        <div className="container mx-auto px-6 relative z-10">
                            <SectionTitle 
                                subtitle="HOW IT WORKS" 
                                title="휴먼 센서 시스템" 
                                description="기술(Tech)과 사람(Human)이 결합된 가장 완벽한 데이터 파이프라인입니다."
                            />

                            <div className="grid md:grid-cols-3 gap-12 mt-16">
                                <div className="relative">
                                    <div className="aspect-video bg-slate-900 rounded-2xl overflow-hidden mb-8 shadow-2xl relative group">
                                        <img src="https://images.unsplash.com/photo-1451187580459-43490279c0fa?q=80&w=2072&auto=format&fit=crop" className="w-full h-full object-cover opacity-60 group-hover:scale-105 transition duration-500" alt="AI Sorting" />
                                        <div className="absolute inset-0 flex flex-col justify-center items-center text-white p-6">
                                            <i className="ri-node-tree text-5xl mb-4 text-blue-400"></i>
                                            <h4 className="text-xl font-bold">Step 1. AI 경로 최적화</h4>
                                        </div>
                                    </div>
                                    <p className="text-slate-600">산발적으로 발생한 도시 문제들을 AI가 분석하여, 시니어 요원에게 <strong>'최적의 순찰 경로'</strong>를 배정합니다.</p>
                                </div>
                                <div className="relative">
                                    <div className="aspect-video bg-slate-900 rounded-2xl overflow-hidden mb-8 shadow-2xl relative group">
                                        <img src="https://images.unsplash.com/photo-1555212697-194d092e3b8f?q=80&w=2574&auto=format&fit=crop" className="w-full h-full object-cover opacity-60 group-hover:scale-105 transition duration-500" alt="Human Sensing" />
                                        <div className="absolute inset-0 flex flex-col justify-center items-center text-white p-6">
                                            <i className="ri-scan-line text-5xl mb-4 text-orange-400"></i>
                                            <h4 className="text-xl font-bold">Step 2. AR 정밀 수집</h4>
                                        </div>
                                    </div>
                                    <p className="text-slate-600">시니어 전용 앱의 <strong>AR 가이드라인</strong>을 통해 누구나 전문가처럼 시설물을 점검하고 데이터를 수집합니다.</p>
                                </div>
                                <div className="relative">
                                    <div className="aspect-video bg-slate-900 rounded-2xl overflow-hidden mb-8 shadow-2xl relative group">
                                        <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?q=80&w=2670&auto=format&fit=crop" className="w-full h-full object-cover opacity-60 group-hover:scale-105 transition duration-500" alt="Auto Report" />
                                        <div className="absolute inset-0 flex flex-col justify-center items-center text-white p-6">
                                            <i className="ri-file-text-line text-5xl mb-4 text-green-400"></i>
                                            <h4 className="text-xl font-bold">Step 3. 자동 리포팅</h4>
                                        </div>
                                    </div>
                                    <p className="text-slate-600">수집된 데이터는 실시간으로 전송되며, <strong>'관공서 제출용 보고서(HWP)'</strong>가 1초 만에 자동 생성됩니다.</p>
                                </div>
                            </div>
                        </div>
                    </section>

                    {/* 5. DATA PREVIEW */}
                    <section id="data" className="py-24 bg-slate-900 text-white">
                        <div className="container mx-auto px-6">
                            <div className="flex flex-col md:flex-row justify-between items-end mb-12">
                                <div>
                                    <span className="text-orange-500 font-bold mb-2 block tracking-widest text-sm">DATA INTELLIGENCE</span>
                                    <h2 className="text-4xl font-bold">실시간 수집 데이터 현황</h2>
                                </div>
                                <div className="text-right">
                                    <p className="text-slate-400 text-sm mb-1">Total Records Today</p>
                                    <p className="text-4xl font-mono font-bold text-white">2,542 <span className="text-lg text-slate-500 font-normal">건</span></p>
                                </div>
                            </div>

                            <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                                {logs.map((log, i) => (
                                    <div key={i} className="bg-slate-800 p-6 rounded-xl border border-slate-700 hover:border-orange-500/50 transition duration-300">
                                        <div className="flex justify-between items-start mb-4">
                                            <Badge color={log.status === '긴급' ? 'red' : log.status === '주의' ? 'orange' : 'green'}>{log.status}</Badge>
                                            <span className="text-xs text-slate-500 font-mono">{log.time}</span>
                                        </div>
                                        <h4 className="text-xl font-bold mb-1">{log.item}</h4>
                                        <p className="text-slate-400 text-sm mb-4">{log.loc}</p>
                                        <div className="text-xs text-slate-500 font-mono pt-4 border-t border-slate-700 flex justify-between">
                                            <span>CODE: {log.id}</span>
                                            <span>CAT: {log.cat}</span>
                                        </div>
                                    </div>
                                ))}
                            </div>
                        </div>
                    </section>

                    {/* 6. APP TECH */}
                    <section id="features" className="py-24 bg-white overflow-hidden">
                        <div className="container mx-auto px-6">
                            <div className="flex flex-col lg:flex-row items-center gap-16">
                                <div className="lg:w-1/2 relative">
                                    {/* Abstract Phone Mockup */}
                                    <div className="relative mx-auto border-gray-800 dark:border-gray-800 bg-gray-800 border-[14px] rounded-[2.5rem] h-[600px] w-[300px] shadow-2xl">
                                        <div className="w-[148px] h-[18px] bg-gray-800 top-0 rounded-b-[1rem] left-1/2 -translate-x-1/2 absolute"></div>
                                        <div className="rounded-[2rem] overflow-hidden w-[272px] h-[572px] bg-white relative">
                                            <div className="absolute inset-0 bg-slate-900 flex flex-col">
                                                <div className="flex-1 bg-slate-800 relative flex items-center justify-center">
                                                    <div className="w-48 h-48 border-2 border-green-400 rounded-lg flex items-center justify-center relative">
                                                        <div className="absolute top-0 left-0 w-4 h-4 border-t-4 border-l-4 border-green-400 -mt-1 -ml-1"></div>
                                                        <div className="absolute top-0 right-0 w-4 h-4 border-t-4 border-r-4 border-green-400 -mt-1 -mr-1"></div>
                                                        <div className="absolute bottom-0 left-0 w-4 h-4 border-b-4 border-l-4 border-green-400 -mb-1 -ml-1"></div>
                                                        <div className="absolute bottom-0 right-0 w-4 h-4 border-b-4 border-r-4 border-green-400 -mb-1 -mr-1"></div>
                                                        <span className="bg-green-500 text-white text-xs px-2 py-1 rounded absolute -top-8 animate-pulse">포트홀 감지됨</span>
                                                    </div>
                                                    <div className="absolute bottom-4 w-full px-4">
                                                        <div className="bg-black/60 text-white text-xs p-3 rounded backdrop-blur-sm">
                                                            <p className="font-bold text-green-400 mb-1">💡 AR 촬영 가이드</p>
                                                            <p>박스 안에 파손 부위를 맞춰주세요.</p>
                                                        </div>
                                                    </div>
                                                </div>
                                                <div className="h-32 bg-white flex items-center justify-center p-4">
                                                    <div className="w-20 h-20 bg-white border-4 border-slate-200 rounded-full flex items-center justify-center shadow-lg active:scale-95 transition cursor-pointer">
                                                        <div className="w-16 h-16 bg-red-500 rounded-full"></div>
                                                    </div>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                                <div className="lg:w-1/2">
                                    <SectionTitle 
                                        align="left"
                                        subtitle="SENIOR-FRIENDLY UX" 
                                        title="디지털 소외 없는, 직관적인 전용 앱" 
                                        description="복잡한 기능은 빼고, 안전과 데이터에만 집중했습니다. 70대 어르신도 10분 교육이면 능숙하게 사용합니다."
                                    />
                                    
                                    <div className="space-y-8 mt-8">
                                        <div className="flex gap-6">
                                            <div className="w-12 h-12 rounded-full bg-blue-100 flex items-center justify-center text-blue-600 text-xl font-bold shrink-0">1</div>
                                            <div>
                                                <h4 className="text-xl font-bold mb-2">AR 가이드 촬영</h4>
                                                <p className="text-slate-600">카메라 화면에 촬영 가이드라인이 표시되어, 흔들림 없고 정확한 앵글의 사진을 확보합니다.</p>
                                            </div>
                                        </div>
                                        <div className="flex gap-6">
                                            <div className="w-12 h-12 rounded-full bg-green-100 flex items-center justify-center text-green-600 text-xl font-bold shrink-0">2</div>
                                            <div>
                                                <h4 className="text-xl font-bold mb-2">건강 모니터링 (Safety First)</h4>
                                                <p className="text-slate-600">활동 중 시니어의 이동 거리와 속도를 분석하여, 이상 징후 발생 시 즉시 관리자에게 알림을 보냅니다.</p>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </section>

                    {/* 7. TARGET & SOLUTIONS (Combined View) */}
                    <section id="contact" className="py-24 bg-slate-50">
                        <div className="container mx-auto px-6 max-w-7xl">
                            <SectionTitle 
                                title="맞춤형 도입 플랜" 
                                description="공공기관의 명분과 기업의 실리, 실버가드가 모두 충족시킵니다."
                            />

                            <div className="grid md:grid-cols-2 gap-8 lg:gap-12">
                                {/* B2G Card */}
                                <div className="bg-white rounded-3xl p-10 border border-slate-200 shadow-lg hover:shadow-xl transition duration-300 relative overflow-hidden group">
                                    <div className="absolute top-0 left-0 w-full h-2 bg-blue-600"></div>
                                    <div className="mb-8">
                                        <span className="inline-block py-1 px-3 rounded bg-blue-100 text-blue-700 font-bold tracking-wider text-xs mb-4">FOR GOVERNMENT</span>
                                        <h3 className="text-3xl font-bold text-slate-900 mb-2">지자체 / 공공기관</h3>
                                        <p className="text-slate-500 font-medium">안심 동네 시범사업 패키지</p>
                                    </div>
                                    
                                    <div className="space-y-6 mb-10">
                                        <div className="flex items-start gap-4">
                                            <i className="ri-government-line text-blue-600 text-2xl"></i>
                                            <div>
                                                <strong className="block text-lg text-slate-900 mb-1">예산 효율화 (국비 매칭)</strong>
                                                <p className="text-slate-600 text-sm">사회서비스형 선도모델 지침에 의거, 구비 부담을 최소화하고 국비 지원을 연계합니다.</p>
                                            </div>
                                        </div>
                                        <div className="flex items-start gap-4">
                                            <i className="ri-shield-check-line text-blue-600 text-2xl"></i>
                                            <div>
                                                <strong className="block text-lg text-slate-900 mb-1">적극행정 면책 근거</strong>
                                                <p className="text-slate-600 text-sm">데이터 기반의 선제적 관리 실적으로 감사 지적 사항을 사전에 방어합니다.</p>
                                            </div>
                                        </div>
                                        <div className="flex items-start gap-4">
                                            <i className="ri-emotion-happy-line text-blue-600 text-2xl"></i>
                                            <div>
                                                <strong className="block text-lg text-slate-900 mb-1">민원 사전 예방</strong>
                                                <p className="text-slate-600 text-sm">주민 신고 전 선제적 조치로 악성 민원을 30% 이상 감소시킵니다.</p>
                                            </div>
                                        </div>
                                    </div>

                                    <button className="w-full bg-slate-900 hover:bg-blue-900 text-white py-4 rounded-xl font-bold transition flex items-center justify-center gap-2 group-hover:scale-[1.02] duration-300">
                                        시범사업 제안서 요청 <i className="ri-arrow-right-line"></i>
                                    </button>
                                </div>

                                {/* B2B Card */}
                                <div className="bg-slate-900 rounded-3xl p-10 border border-slate-700 shadow-2xl relative overflow-hidden group text-white">
                                    <div className="absolute top-0 left-0 w-full h-2 bg-orange-500"></div>
                                    <div className="mb-8">
                                        <span className="inline-block py-1 px-3 rounded bg-orange-900/50 text-orange-400 border border-orange-500/30 font-bold tracking-wider text-xs mb-4">FOR BUSINESS</span>
                                        <h3 className="text-3xl font-bold text-white mb-2">위탁 관리 기업</h3>
                                        <p className="text-slate-400 font-medium">스마트 순찰 구독 솔루션</p>
                                    </div>
                                    
                                    <div className="space-y-6 mb-10">
                                        <div className="flex items-start gap-4">
                                            <i className="ri-money-dollar-box-line text-orange-500 text-2xl"></i>
                                            <div>
                                                <strong className="block text-lg text-white mb-1">압도적인 비용 절감</strong>
                                                <p className="text-slate-400 text-sm">정규직 1명 채용 비용의 절반 이하로 5명의 전담 순찰대를 운용하는 효과를 누리세요.</p>
                                            </div>
                                        </div>
                                        <div className="flex items-start gap-4">
                                            <i className="ri-file-word-2-line text-orange-500 text-2xl"></i>
                                            <div>
                                                <strong className="block text-lg text-white mb-1">보고서 100% 자동화</strong>
                                                <p className="text-slate-400 text-sm">현장 사진 찍으면 '구청 제출용 HWP'가 자동 생성됩니다. 더 이상 야근하지 마십시오.</p>
                                            </div>
                                        </div>
                                        <div className="flex items-start gap-4">
                                            <i className="ri-hammer-line text-orange-500 text-2xl"></i>
                                            <div>
                                                <strong className="block text-lg text-white mb-1">중대재해법 리스크 방어</strong>
                                                <p className="text-slate-400 text-sm">"우리는 확실히 점검했다"는 완벽한 디지털 증거(Log)를 제공해 드립니다.</p>
                                            </div>
                                        </div>
                                    </div>

                                    <button className="w-full bg-orange-600 hover:bg-orange-700 text-white py-4 rounded-xl font-bold transition flex items-center justify-center gap-2 group-hover:scale-[1.02] duration-300 shadow-lg shadow-orange-900/50">
                                        무료 데모 / 견적 신청 <i className="ri-arrow-right-line"></i>
                                    </button>
                                </div>
                            </div>
                        </div>
                    </section>

                    {/* 8. FOOTER */}
                    <footer className="bg-slate-900 text-white py-20 border-t border-slate-800">
                        <div className="container mx-auto px-6">
                            <div className="flex flex-col md:flex-row justify-between items-center gap-8 border-b border-slate-800 pb-12 mb-12">
                                <div>
                                    <h4 className="text-3xl font-bold mb-2">Silver Guard</h4>
                                    <p className="text-slate-400">Data for Safe City, Jobs for Senior Dignity.</p>
                                </div>
                                <div className="flex gap-4">
                                    <span className="px-4 py-2 border border-slate-700 rounded-full text-xs text-slate-400">보건복지부 연계</span>
                                    <span className="px-4 py-2 border border-slate-700 rounded-full text-xs text-slate-400">행정안전부 표준</span>
                                </div>
                            </div>
                            <div className="grid md:grid-cols-3 gap-12 text-sm text-slate-400">
                                <div>
                                    <h5 className="font-bold text-white mb-4">Contact Us</h5>
                                    <p className="mb-2">contact@silverguard.co.kr</p>
                                    <p>02-1234-5678</p>
                                    <p>서울시 강남구 테헤란로</p>
                                </div>
                                <div>
                                    <h5 className="font-bold text-white mb-4">Solutions</h5>
                                    <p className="mb-2">도로/교통 위험 감지</p>
                                    <p className="mb-2">환경/안전 모니터링</p>
                                    <p>시설물 유지보수</p>
                                </div>
                                <div>
                                    <h5 className="font-bold text-white mb-4">Legal</h5>
                                    <p className="mb-2">개인정보처리방침</p>
                                    <p>서비스 이용약관</p>
                                </div>
                            </div>
                            <div className="mt-12 text-center text-xs text-slate-600">
                                &copy; 2024 Silver Guard Lab. All rights reserved.
                            </div>
                        </div>
                    </footer>
                </div>
            );
        };

        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(<App />);
    </script>
</body>
</html>

