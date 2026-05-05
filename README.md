<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sayan Ghosh — AI Engineer & ML Researcher</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800;900&family=JetBrains+Mono:wght@400;500;700&display=swap" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
<script src="https://unpkg.com/lucide@latest"></script>
<script>
tailwind.config = {
    theme: {
        extend: {
            fontFamily: {
                'outfit': ['Outfit', 'sans-serif'],
                'mono': ['JetBrains Mono', 'monospace'],
            },
            colors: {
                'brand': {
                    50: '#f0f7ff', 100: '#e0efff', 200: '#b8ddff', 300: '#7ac2ff',
                    400: '#36a3ff', 500: '#0d8af2', 600: '#006fd1', 700: '#0058a8',
                    800: '#064a8a', 900: '#0a3f72',
                },
                'accent': { orange: '#FF6B35', purple: '#8B5CF6', teal: '#14B8A6', rose: '#F43F5E' }
            }
        }
    }
}
</script>
<style>
:root { --bg-primary: #0a0e17; --bg-secondary: #0d1117; --bg-card: #111827; --border: #1e293b; --text-primary: #f1f5f9; --text-secondary: #94a3b8; --text-muted: #64748b; }
* { margin: 0; padding: 0; box-sizing: border-box; }
html { scroll-behavior: smooth; }
body { font-family: 'Outfit', sans-serif; background: var(--bg-primary); color: var(--text-primary); overflow-x: hidden; line-height: 1.6; }
#particles-canvas { position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 0; pointer-events: none; }
.glass { background: rgba(17,24,39,0.6); backdrop-filter: blur(20px); -webkit-backdrop-filter: blur(20px); border: 1px solid rgba(255,255,255,0.05); }
.glass-strong { background: rgba(17,24,39,0.85); backdrop-filter: blur(30px); -webkit-backdrop-filter: blur(30px); border: 1px solid rgba(255,255,255,0.08); }
.glow-brand { box-shadow: 0 0 40px rgba(13,138,242,0.15), 0 0 80px rgba(13,138,242,0.05); }
.text-glow { text-shadow: 0 0 30px rgba(13,138,242,0.3), 0 0 60px rgba(13,138,242,0.1); }
.gradient-text { background: linear-gradient(135deg, #0d8af2 0%, #7ac2ff 50%, #14B8A6 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }
.gradient-text-warm { background: linear-gradient(135deg, #FF6B35 0%, #F43F5E 50%, #8B5CF6 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }
.gradient-border { position: relative; background: var(--bg-card); border-radius: 16px; overflow: hidden; }
.gradient-border::before { content: ''; position: absolute; inset: 0; border-radius: 16px; padding: 1.5px; background: linear-gradient(135deg, #0d8af2, #14B8A6, #8B5CF6, #FF6B35, #0d8af2); background-size: 300% 300%; animation: gradientRotate 6s linear infinite; -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0); -webkit-mask-composite: xor; mask-composite: exclude; pointer-events: none; }
@keyframes gradientRotate { 0%{background-position:0% 50%} 50%{background-position:100% 50%} 100%{background-position:0% 50%} }
@keyframes float { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-20px)} }
.float-animation { animation: float 6s ease-in-out infinite; }
.float-animation-delay { animation: float 6s ease-in-out infinite; animation-delay: -3s; }
@keyframes pulseGlow { 0%,100%{box-shadow:0 0 20px rgba(13,138,242,0.2)} 50%{box-shadow:0 0 40px rgba(13,138,242,0.4),0 0 60px rgba(13,138,242,0.1)} }
.pulse-glow { animation: pulseGlow 3s ease-in-out infinite; }
@keyframes shimmer { 0%{background-position:-200% 0} 100%{background-position:200% 0} }
.shimmer { background: linear-gradient(90deg, transparent 0%, rgba(255,255,255,0.05) 50%, transparent 100%); background-size: 200% 100%; animation: shimmer 3s infinite; }
@keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }
.cursor-blink { animation: blink 1s step-end infinite; }
@keyframes orbit { 0%{transform:rotate(0deg) translateX(80px) rotate(0deg)} 100%{transform:rotate(360deg) translateX(80px) rotate(-360deg)} }
.orbit-dot { animation: orbit 12s linear infinite; }
.orbit-dot:nth-child(2){animation-delay:-4s} .orbit-dot:nth-child(3){animation-delay:-8s}
.project-card { transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
.project-card:hover { transform: translateY(-12px) scale(1.02); }
.nav-link { position: relative; overflow: hidden; }
.nav-link::after { content: ''; position: absolute; bottom: -2px; left: 50%; width: 0; height: 2px; background: linear-gradient(90deg, #0d8af2, #14B8A6); transition: all 0.3s ease; transform: translateX(-50%); }
.nav-link:hover::after { width: 100%; }
::-webkit-scrollbar { width: 8px; }
::-webkit-scrollbar-track { background: var(--bg-primary); }
::-webkit-scrollbar-thumb { background: linear-gradient(180deg, #0d8af2, #8B5CF6); border-radius: 4px; }
.reveal { opacity: 0; transform: translateY(40px); }
.badge-hover { transition: all 0.3s ease; }
.badge-hover:hover { transform: translateY(-3px); box-shadow: 0 10px 30px rgba(13,138,242,0.2); }
.contact-btn { position: relative; overflow: hidden; transition: all 0.3s ease; }
.contact-btn::before { content: ''; position: absolute; top: 0; left: -100%; width: 100%; height: 100%; background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent); transition: left 0.5s ease; }
.contact-btn:hover::before { left: 100%; }
.hero-orbit-container { position: relative; width: 300px; height: 300px; }
.hero-center { position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); z-index: 2; }
.orbit-ring { position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); border: 1px solid rgba(13,138,242,0.15); border-radius: 50%; }
.tooltip { position: relative; }
.tooltip::after { content: attr(data-tooltip); position: absolute; bottom: 100%; left: 50%; transform: translateX(-50%) translateY(-8px); padding: 6px 12px; background: var(--bg-card); border: 1px solid var(--border); border-radius: 8px; font-size: 12px; white-space: nowrap; opacity: 0; pointer-events: none; transition: all 0.3s ease; }
.tooltip:hover::after { opacity: 1; transform: translateX(-50%) translateY(-4px); }
</style>
<base target="_blank">
</head>
<body>
<canvas id="particles-canvas"></canvas>

<!-- NAVIGATION -->
<nav id="navbar" class="fixed top-0 left-0 w-full z-50 transition-all duration-500 opacity-0 -translate-y-full">
    <div class="glass-strong">
        <div class="max-w-7xl mx-auto px-6 py-4 flex items-center justify-between">
            <a href="#" class="text-xl font-bold font-outfit gradient-text">SG.</a>
            <div class="hidden md:flex items-center gap-8">
                <a href="#about" class="nav-link text-sm font-medium text-slate-300 hover:text-white transition-colors">About</a>
                <a href="#skills" class="nav-link text-sm font-medium text-slate-300 hover:text-white transition-colors">Skills</a>
                <a href="#projects" class="nav-link text-sm font-medium text-slate-300 hover:text-white transition-colors">Projects</a>
                <a href="#stats" class="nav-link text-sm font-medium text-slate-300 hover:text-white transition-colors">Stats</a>
                <a href="#contact" class="px-5 py-2 rounded-full bg-gradient-to-r from-brand-500 to-brand-600 text-white text-sm font-semibold hover:shadow-lg hover:shadow-brand-500/25 transition-all">Let's Talk</a>
            </div>
            <button id="mobile-menu-btn" class="md:hidden text-white">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="4" x2="20" y1="12" y2="12"/><line x1="4" x2="20" y1="6" y2="6"/><line x1="4" x2="20" y1="18" y2="18"/></svg>
            </button>
        </div>
    </div>
</nav>

<div id="mobile-menu" class="fixed inset-0 z-40 glass-strong hidden flex-col items-center justify-center gap-8">
    <a href="#about" class="text-2xl font-medium text-white mobile-link">About</a>
    <a href="#skills" class="text-2xl font-medium text-white mobile-link">Skills</a>
    <a href="#projects" class="text-2xl font-medium text-white mobile-link">Projects</a>
    <a href="#stats" class="text-2xl font-medium text-white mobile-link">Stats</a>
    <a href="#contact" class="text-2xl font-medium text-white mobile-link">Contact</a>
    <button id="mobile-menu-close" class="absolute top-6 right-6 text-white">
        <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 6 6 18"/><path d="m6 6 12 12"/></svg>
    </button>
</div>

<!-- HERO SECTION -->
<section id="hero" class="relative min-h-screen flex items-center justify-center overflow-hidden">
    <div class="absolute top-1/4 left-1/4 w-96 h-96 bg-brand-500/10 rounded-full blur-[120px]"></div>
    <div class="absolute bottom-1/4 right-1/4 w-96 h-96 bg-accent-purple/10 rounded-full blur-[120px]"></div>
    <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[600px] h-[600px] bg-accent-teal/5 rounded-full blur-[150px]"></div>

    <div class="relative z-10 max-w-7xl mx-auto px-6 py-20 grid lg:grid-cols-2 gap-12 items-center">
        <div class="text-center lg:text-left">
            <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full glass mb-6 hero-badge">
                <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span>
                <span class="text-sm font-medium text-slate-300">Available for opportunities</span>
            </div>
            <h1 class="text-5xl md:text-7xl lg:text-8xl font-black font-outfit leading-tight mb-4">
                <span class="block text-white hero-title-1">SAYAN</span>
                <span class="block gradient-text text-glow hero-title-2">GHOSH</span>
            </h1>
            <div class="h-12 md:h-16 flex items-center justify-center lg:justify-start mb-8">
                <span id="typewriter" class="text-xl md:text-2xl lg:text-3xl font-mono font-medium text-slate-400"></span>
                <span class="w-1 h-8 bg-brand-400 cursor-blink ml-1"></span>
            </div>
            <p class="text-lg text-slate-400 max-w-xl mx-auto lg:mx-0 mb-10 hero-desc">
                CS undergrad at <span class="text-brand-400 font-semibold">KIIT University</span> (Class of 2027). Building intelligent systems that solve real problems. Obsessed with AI, ML, and scalable solutions.
            </p>
            <div class="flex flex-wrap gap-4 justify-center lg:justify-start hero-buttons">
                <a href="#projects" class="contact-btn px-8 py-4 rounded-full bg-gradient-to-r from-brand-500 to-brand-600 text-white font-semibold hover:shadow-xl hover:shadow-brand-500/30 transition-all flex items-center gap-2">
                    <span>View My Work</span>
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>
                </a>
                <a href="#contact" class="contact-btn px-8 py-4 rounded-full glass text-white font-semibold hover:border-brand-400/50 transition-all flex items-center gap-2">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
                    <span>Get In Touch</span>
                </a>
            </div>
            <div class="flex gap-4 justify-center lg:justify-start mt-10 hero-social">
                <a href="https://github.com/Sayan-2607" target="_blank" class="w-12 h-12 rounded-xl glass flex items-center justify-center text-slate-400 hover:text-white hover:border-brand-400/50 transition-all tooltip" data-tooltip="GitHub">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"/><path d="M9 18c-4.51 2-5-2-7-2"/></svg>
                </a>
                <a href="https://www.linkedin.com/in/sayan-g-600ab5307/" target="_blank" class="w-12 h-12 rounded-xl glass flex items-center justify-center text-slate-400 hover:text-white hover:border-brand-400/50 transition-all tooltip" data-tooltip="LinkedIn">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect width="4" height="12" x="2" y="9"/><circle cx="4" cy="4" r="2"/></svg>
                </a>
                <a href="https://www.instagram.com/quantx.exe?igsh=bXJmcHY4dzI5ZHgw" target="_blank" class="w-12 h-12 rounded-xl glass flex items-center justify-center text-slate-400 hover:text-white hover:border-brand-400/50 transition-all tooltip" data-tooltip="Instagram">
                        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>
                    </a>
                <a href="mailto:sayanghosh2607@gmail.com" class="w-12 h-12 rounded-xl glass flex items-center justify-center text-slate-400 hover:text-white hover:border-brand-400/50 transition-all tooltip" data-tooltip="Email">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
                </a>
            </div>
        </div>

        <div class="relative flex items-center justify-center hero-visual">
            <div class="hero-orbit-container">
                <div class="orbit-ring w-[300px] h-[300px]"></div>
                <div class="orbit-ring w-[220px] h-[220px] opacity-50"></div>
                <div class="orbit-ring w-[140px] h-[140px] opacity-30"></div>
                <div class="hero-center">
                    <div class="w-24 h-24 md:w-32 md:h-32 rounded-full bg-gradient-to-br from-brand-400 via-brand-500 to-accent-purple flex items-center justify-center pulse-glow">
                        <span class="text-4xl md:text-5xl font-black text-white">SG</span>
                    </div>
                </div>
                <div class="orbit-dot absolute top-1/2 left-1/2">
                    <div class="w-12 h-12 rounded-xl glass flex items-center justify-center text-brand-400 shadow-lg shadow-brand-500/20">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 5a3 3 0 1 0-5.997.125 4 4 0 0 0-2.526 5.77 4 4 0 0 0 .556 6.588A4 4 0 1 0 12 18Z"/><path d="M12 5a3 3 0 1 1 5.997.125 4 4 0 0 1 2.526 5.77 4 4 0 0 1-.556 6.588A4 4 0 1 1 12 18Z"/></svg>
                    </div>
                </div>
                <div class="orbit-dot absolute top-1/2 left-1/2">
                    <div class="w-12 h-12 rounded-xl glass flex items-center justify-center text-accent-purple shadow-lg shadow-accent-purple/20">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m18 16 4-4-4-4"/><path d="m6 8-4 4 4 4"/><path d="m14.5 4-5 16"/></svg>
                    </div>
                </div>
                <div class="orbit-dot absolute top-1/2 left-1/2">
                    <div class="w-12 h-12 rounded-xl glass flex items-center justify-center text-accent-teal shadow-lg shadow-accent-teal/20">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><ellipse cx="12" cy="5" rx="9" ry="3"/><path d="M3 5V19A9 3 0 0 0 21 19V5"/><path d="M3 12A9 3 0 0 0 21 12"/></svg>
                    </div>
                </div>
            </div>
            <div class="absolute -top-4 -right-4 md:right-0 glass rounded-2xl p-4 float-animation">
                <div class="flex items-center gap-3">
                    <div class="w-10 h-10 rounded-lg bg-brand-500/20 flex items-center justify-center">
                        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="22 7 13.5 15.5 8.5 10.5 2 17"/><polyline points="16 7 22 7 22 13"/></svg>
                    </div>
                    <div>
                        <p class="text-xs text-slate-400">ML Projects</p>
                        <p class="text-lg font-bold text-white">15+</p>
                    </div>
                </div>
            </div>
            <div class="absolute -bottom-4 -left-4 md:left-0 glass rounded-2xl p-4 float-animation-delay">
                <div class="flex items-center gap-3">
                    <div class="w-10 h-10 rounded-lg bg-accent-purple/20 flex items-center justify-center">
                        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="8" r="6"/><path d="M15.477 12.89 17 22l-5-3-5 3 1.523-9.11"/></svg>
                    </div>
                    <div>
                        <p class="text-xs text-slate-400">Research</p>
                        <p class="text-lg font-bold text-white">Active</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 flex flex-col items-center gap-2 opacity-60">
        <span class="text-xs text-slate-500 font-mono">SCROLL</span>
        <div class="w-6 h-10 rounded-full border-2 border-slate-600 flex justify-center pt-2">
            <div class="w-1.5 h-3 bg-brand-400 rounded-full animate-bounce"></div>
        </div>
    </div>
</section>

<!-- ABOUT SECTION -->
<section id="about" class="relative py-24 md:py-32">
    <div class="max-w-7xl mx-auto px-6">
        <div class="grid lg:grid-cols-2 gap-16 items-center">
            <div class="relative reveal">
                <div class="relative z-10">
                    <div class="gradient-border p-1">
                        <div class="bg-[#111827] rounded-[14px] p-8 md:p-12">
                            <div class="grid grid-cols-2 gap-6">
                                <div class="space-y-6">
                                    <div class="glass rounded-2xl p-5 text-center hover:border-brand-400/30 transition-all">
                                        <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-brand-400 mx-auto mb-2"><path d="M12 5a3 3 0 1 0-5.997.125 4 4 0 0 0-2.526 5.77 4 4 0 0 0 .556 6.588A4 4 0 1 0 12 18Z"/><path d="M12 5a3 3 0 1 1 5.997.125 4 4 0 0 1 2.526 5.77 4 4 0 0 1-.556 6.588A4 4 0 1 1 12 18Z"/></svg>
                                        <p class="text-sm font-semibold text-white">Machine Learning</p>
                                        <p class="text-xs text-slate-500 mt-1">Deep expertise</p>
                                    </div>
                                    <div class="glass rounded-2xl p-5 text-center hover:border-accent-purple/30 transition-all">
                                        <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-accent-purple mx-auto mb-2"><path d="M2 12s3-7 10-7 10 7 10 7-3 7-10 7-10-7-10-7Z"/><circle cx="12" cy="12" r="3"/></svg>
                                        <p class="text-sm font-semibold text-white">Computer Vision</p>
                                        <p class="text-xs text-slate-500 mt-1">Image & Video AI</p>
                                    </div>
                                </div>
                                <div class="space-y-6 mt-8">
                                    <div class="glass rounded-2xl p-5 text-center hover:border-accent-teal/30 transition-all">
                                        <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-accent-teal mx-auto mb-2"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
                                        <p class="text-sm font-semibold text-white">NLP</p>
                                        <p class="text-xs text-slate-500 mt-1">Language models</p>
                                    </div>
                                    <div class="glass rounded-2xl p-5 text-center hover:border-accent-orange/30 transition-all">
                                        <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-accent-orange mx-auto mb-2"><rect width="20" height="8" x="2" y="2" rx="2" ry="2"/><rect width="20" height="8" x="2" y="14" rx="2" ry="2"/><line x1="6" x2="6.01" y1="6" y2="6"/><line x1="6" x2="6.01" y1="18" y2="18"/></svg>
                                        <p class="text-sm font-semibold text-white">MLOps</p>
                                        <p class="text-xs text-slate-500 mt-1">Scalable deployment</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="absolute -top-6 -left-6 w-24 h-24 border border-brand-500/20 rounded-2xl"></div>
                <div class="absolute -bottom-6 -right-6 w-32 h-32 border border-accent-purple/20 rounded-full"></div>
            </div>

            <div class="reveal">
                <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full glass mb-6">
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-brand-400"><path d="M19 21v-2a4 4 0 0 0-4-4H9a4 4 0 0 0-4 4v2"/><circle cx="12" cy="7" r="4"/></svg>
                    <span class="text-sm font-medium text-slate-300">Who I Am</span>
                </div>
                <h2 class="text-4xl md:text-5xl font-bold font-outfit mb-6">Engineering <span class="gradient-text">Intelligence</span><br>for the Real World</h2>
                <p class="text-slate-400 text-lg mb-6 leading-relaxed">I'm a passionate <span class="text-white font-semibold">CS undergrad at KIIT University</span> (Class of 2027), obsessed with building intelligent systems that solve real problems. My journey in AI started with curiosity and evolved into a mission to make technology accessible and impactful.</p>
                <p class="text-slate-400 text-lg mb-8 leading-relaxed">From predicting customer churn to building health sensing systems, I believe in AI that creates tangible value. Currently exploring <span class="text-brand-400 font-medium">Deep Learning architectures</span> and <span class="text-brand-400 font-medium">MLOps</span> to scale solutions that matter.</p>
                <div class="grid grid-cols-2 gap-4 mb-8">
                    <div class="glass rounded-xl p-4 border-l-4 border-brand-500">
                        <p class="text-2xl font-bold text-white">4+</p>
                        <p class="text-sm text-slate-400">Years Coding</p>
                    </div>
                    <div class="glass rounded-xl p-4 border-l-4 border-accent-purple">
                        <p class="text-2xl font-bold text-white">15+</p>
                        <p class="text-sm text-slate-400">ML Projects</p>
                    </div>
                    <div class="glass rounded-xl p-4 border-l-4 border-accent-teal">
                        <p class="text-2xl font-bold text-white">3+</p>
                        <p class="text-sm text-slate-400">Research Areas</p>
                    </div>
                    <div class="glass rounded-xl p-4 border-l-4 border-accent-orange">
                        <p class="text-2xl font-bold text-white">∞</p>
                        <p class="text-sm text-slate-400">Curiosity</p>
                    </div>
                </div>
                <blockquote class="border-l-4 border-brand-500 pl-6 py-2 italic text-slate-300 text-lg">"I don't just write code — I engineer intelligence."</blockquote>
            </div>
        </div>
    </div>
</section>

<!-- SKILLS SECTION -->
<section id="skills" class="relative py-24 md:py-32">
    <div class="absolute inset-0 bg-gradient-to-b from-transparent via-brand-500/5 to-transparent"></div>
    <div class="relative max-w-7xl mx-auto px-6">
        <div class="text-center mb-16 reveal">
            <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full glass mb-6">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-brand-400"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>
                <span class="text-sm font-medium text-slate-300">Tech Stack</span>
            </div>
            <h2 class="text-4xl md:text-5xl font-bold font-outfit mb-4">My <span class="gradient-text">Tech DNA</span></h2>
            <p class="text-slate-400 text-lg max-w-2xl mx-auto">A versatile toolkit spanning AI/ML, software development, and DevOps — built for building production-ready solutions.</p>
        </div>

        <div class="grid md:grid-cols-3 gap-8">
            <!-- AI/ML -->
            <div class="reveal">
                <div class="gradient-border h-full">
                    <div class="bg-[#111827] rounded-[14px] p-8 h-full">
                        <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-brand-500/20 to-brand-600/20 flex items-center justify-center mb-6">
                            <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-brand-400"><path d="M12 5a3 3 0 1 0-5.997.125 4 4 0 0 0-2.526 5.77 4 4 0 0 0 .556 6.588A4 4 0 1 0 12 18Z"/><path d="M12 5a3 3 0 1 1 5.997.125 4 4 0 0 1 2.526 5.77 4 4 0 0 1-.556 6.588A4 4 0 1 1 12 18Z"/></svg>
                        </div>
                        <h3 class="text-2xl font-bold text-white mb-2">AI / ML</h3>
                        <p class="text-slate-400 text-sm mb-6">Core machine learning and deep learning expertise</p>
                        <div class="space-y-4">
                            <div><div class="flex justify-between mb-1"><span class="text-sm text-slate-300">Python</span><span class="text-sm text-brand-400 font-mono">95%</span></div><div class="h-2 bg-slate-800 rounded-full overflow-hidden"><div class="h-full bg-gradient-to-r from-brand-500 to-brand-400 rounded-full skill-bar" data-width="95" style="width:0%"></div></div></div>
                            <div><div class="flex justify-between mb-1"><span class="text-sm text-slate-300">TensorFlow</span><span class="text-sm text-brand-400 font-mono">85%</span></div><div class="h-2 bg-slate-800 rounded-full overflow-hidden"><div class="h-full bg-gradient-to-r from-brand-500 to-brand-400 rounded-full skill-bar" data-width="85" style="width:0%"></div></div></div>
                            <div><div class="flex justify-between mb-1"><span class="text-sm text-slate-300">PyTorch</span><span class="text-sm text-brand-400 font-mono">80%</span></div><div class="h-2 bg-slate-800 rounded-full overflow-hidden"><div class="h-full bg-gradient-to-r from-brand-500 to-brand-400 rounded-full skill-bar" data-width="80" style="width:0%"></div></div></div>
                            <div><div class="flex justify-between mb-1"><span class="text-sm text-slate-300">Scikit-Learn</span><span class="text-sm text-brand-400 font-mono">90%</span></div><div class="h-2 bg-slate-800 rounded-full overflow-hidden"><div class="h-full bg-gradient-to-r from-brand-500 to-brand-400 rounded-full skill-bar" data-width="90" style="width:0%"></div></div></div>
                            <div><div class="flex justify-between mb-1"><span class="text-sm text-slate-300">OpenCV</span><span class="text-sm text-brand-400 font-mono">75%</span></div><div class="h-2 bg-slate-800 rounded-full overflow-hidden"><div class="h-full bg-gradient-to-r from-brand-500 to-brand-400 rounded-full skill-bar" data-width="75" style="width:0%"></div></div></div>
                        </div>
                        <div class="flex flex-wrap gap-2 mt-6">
                            <span class="px-3 py-1 rounded-full bg-brand-500/10 text-brand-400 text-xs font-medium">Pandas</span>
                            <span class="px-3 py-1 rounded-full bg-brand-500/10 text-brand-400 text-xs font-medium">NumPy</span>
                            <span class="px-3 py-1 rounded-full bg-brand-500/10 text-brand-400 text-xs font-medium">Matplotlib</span>
                            <span class="px-3 py-1 rounded-full bg-brand-500/10 text-brand-400 text-xs font-medium">Seaborn</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Development -->
            <div class="reveal">
                <div class="gradient-border h-full">
                    <div class="bg-[#111827] rounded-[14px] p-8 h-full">
                        <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-accent-purple/20 to-accent-purple/10 flex items-center justify-center mb-6">
                            <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-accent-purple"><path d="m18 16 4-4-4-4"/><path d="m6 8-4 4 4 4"/><path d="m14.5 4-5 16"/></svg>
                        </div>
                        <h3 class="text-2xl font-bold text-white mb-2">Development</h3>
                        <p class="text-slate-400 text-sm mb-6">Full-stack and systems programming capabilities</p>
                        <div class="space-y-4">
                            <div><div class="flex justify-between mb-1"><span class="text-sm text-slate-300">C++</span><span class="text-sm text-accent-purple font-mono">80%</span></div><div class="h-2 bg-slate-800 rounded-full overflow-hidden"><div class="h-full bg-gradient-to-r from-accent-purple to-violet-400 rounded-full skill-bar" data-width="80" style="width:0%"></div></div></div>
                            <div><div class="flex justify-between mb-1"><span class="text-sm text-slate-300">Java</span><span class="text-sm text-accent-purple font-mono">70%</span></div><div class="h-2 bg-slate-800 rounded-full overflow-hidden"><div class="h-full bg-gradient-to-r from-accent-purple to-violet-400 rounded-full skill-bar" data-width="70" style="width:0%"></div></div></div>
                            <div><div class="flex justify-between mb-1"><span class="text-sm text-slate-300">JavaScript</span><span class="text-sm text-accent-purple font-mono">75%</span></div><div class="h-2 bg-slate-800 rounded-full overflow-hidden"><div class="h-full bg-gradient-to-r from-accent-purple to-violet-400 rounded-full skill-bar" data-width="75" style="width:0%"></div></div></div>
                            <div><div class="flex justify-between mb-1"><span class="text-sm text-slate-300">HTML/CSS</span><span class="text-sm text-accent-purple font-mono">90%</span></div><div class="h-2 bg-slate-800 rounded-full overflow-hidden"><div class="h-full bg-gradient-to-r from-accent-purple to-violet-400 rounded-full skill-bar" data-width="90" style="width:0%"></div></div></div>
                            <div><div class="flex justify-between mb-1"><span class="text-sm text-slate-300">MySQL</span><span class="text-sm text-accent-purple font-mono">70%</span></div><div class="h-2 bg-slate-800 rounded-full overflow-hidden"><div class="h-full bg-gradient-to-r from-accent-purple to-violet-400 rounded-full skill-bar" data-width="70" style="width:0%"></div></div></div>
                        </div>
                        <div class="flex flex-wrap gap-2 mt-6">
                            <span class="px-3 py-1 rounded-full bg-accent-purple/10 text-accent-purple text-xs font-medium">React</span>
                            <span class="px-3 py-1 rounded-full bg-accent-purple/10 text-accent-purple text-xs font-medium">Node.js</span>
                            <span class="px-3 py-1 rounded-full bg-accent-purple/10 text-accent-purple text-xs font-medium">REST APIs</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Tools -->
            <div class="reveal">
                <div class="gradient-border h-full">
                    <div class="bg-[#111827] rounded-[14px] p-8 h-full">
                        <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-accent-teal/20 to-accent-teal/10 flex items-center justify-center mb-6">
                            <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-accent-teal"><path d="M12.22 2h-.44a2 2 0 0 0-2 2v.18a2 2 0 0 1-1 1.73l-.43.25a2 2 0 0 1-2 0l-.15-.08a2 2 0 0 0-2.73.73l-.22.38a2 2 0 0 0 .73 2.73l.15.1a2 2 0 0 1 1 1.72v.51a2 2 0 0 1-1 1.74l-.15.09a2 2 0 0 0-.73 2.73l.22.38a2 2 0 0 0 2.73.73l.15-.08a2 2 0 0 1 2 0l.43.25a2 2 0 0 1 1 1.73V20a2 2 0 0 0 2 2h.44a2 2 0 0 0 2-2v-.18a2 2 0 0 1 1-1.73l.43-.25a2 2 0 0 1 2 0l.15.08a2 2 0 0 0 2.73-.73l.22-.39a2 2 0 0 0-.73-2.73l-.15-.08a2 2 0 0 1-1-1.74v-.5a2 2 0 0 1 1-1.74l.15-.09a2 2 0 0 0 .73-2.73l-.22-.38a2 2 0 0 0-2.73-.73l-.15.08a2 2 0 0 1-2 0l-.43-.25a2 2 0 0 1-1-1.73V4a2 2 0 0 0-2-2z"/><circle cx="12" cy="12" r="3"/></svg>
                        </div>
                        <h3 class="text-2xl font-bold text-white mb-2">Tools & DevOps</h3>
                        <p class="text-slate-400 text-sm mb-6">Development workflow and deployment tools</p>
                        <div class="space-y-4">
                            <div><div class="flex justify-between mb-1"><span class="text-sm text-slate-300">Git & GitHub</span><span class="text-sm text-accent-teal font-mono">90%</span></div><div class="h-2 bg-slate-800 rounded-full overflow-hidden"><div class="h-full bg-gradient-to-r from-accent-teal to-teal-400 rounded-full skill-bar" data-width="90" style="width:0%"></div></div></div>
                            <div><div class="flex justify-between mb-1"><span class="text-sm text-slate-300">VS Code</span><span class="text-sm text-accent-teal font-mono">95%</span></div><div class="h-2 bg-slate-800 rounded-full overflow-hidden"><div class="h-full bg-gradient-to-r from-accent-teal to-teal-400 rounded-full skill-bar" data-width="95" style="width:0%"></div></div></div>
                            <div><div class="flex justify-between mb-1"><span class="text-sm text-slate-300">Jupyter</span><span class="text-sm text-accent-teal font-mono">85%</span></div><div class="h-2 bg-slate-800 rounded-full overflow-hidden"><div class="h-full bg-gradient-to-r from-accent-teal to-teal-400 rounded-full skill-bar" data-width="85" style="width:0%"></div></div></div>
                            <div><div class="flex justify-between mb-1"><span class="text-sm text-slate-300">Docker</span><span class="text-sm text-accent-teal font-mono">65%</span></div><div class="h-2 bg-slate-800 rounded-full overflow-hidden"><div class="h-full bg-gradient-to-r from-accent-teal to-teal-400 rounded-full skill-bar" data-width="65" style="width:0%"></div></div></div>
                            <div><div class="flex justify-between mb-1"><span class="text-sm text-slate-300">Linux</span><span class="text-sm text-accent-teal font-mono">75%</span></div><div class="h-2 bg-slate-800 rounded-full overflow-hidden"><div class="h-full bg-gradient-to-r from-accent-teal to-teal-400 rounded-full skill-bar" data-width="75" style="width:0%"></div></div></div>
                        </div>
                        <div class="flex flex-wrap gap-2 mt-6">
                            <span class="px-3 py-1 rounded-full bg-accent-teal/10 text-accent-teal text-xs font-medium">Bash</span>
                            <span class="px-3 py-1 rounded-full bg-accent-teal/10 text-accent-teal text-xs font-medium">AWS</span>
                            <span class="px-3 py-1 rounded-full bg-accent-teal/10 text-accent-teal text-xs font-medium">CI/CD</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- PROJECTS SECTION -->
<section id="projects" class="relative py-24 md:py-32">
    <div class="max-w-7xl mx-auto px-6">
        <div class="text-center mb-16 reveal">
            <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full glass mb-6">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-accent-orange"><path d="M4.5 16.5c-1.5 1.26-2 5-2 5s3.74-.5 5-2c.71-.84.7-2.13-.09-2.91a2.18 2.18 0 0 0-2.91-.09z"/><path d="m12 15-3-3a22 22 0 0 1 2-3.95A12.88 12.88 0 0 1 22 2c0 2.72-.78 7.5-6 11a22.35 22.35 0 0 1-4 2z"/><path d="M9 12H4s.55-3.03 2-4c1.62-1.08 5 0 5 0"/><path d="M12 15v5s3.03-.55 4-2c1.08-1.62 0-5 0-5"/></svg>
                <span class="text-sm font-medium text-slate-300">Portfolio</span>
            </div>
            <h2 class="text-4xl md:text-5xl font-bold font-outfit mb-4">Signature <span class="gradient-text-warm">Projects</span></h2>
            <p class="text-slate-400 text-lg max-w-2xl mx-auto">Real-world applications built with cutting-edge AI/ML technologies — solving problems that matter.</p>
        </div>

        <div class="grid md:grid-cols-2 gap-8">
            <div class="reveal">
                <a href="https://github.com/Sayan-2607/Predict-Customer-Churn" target="_blank" class="project-card block gradient-border">
                    <div class="bg-[#111827] rounded-[14px] overflow-hidden">
                        <div class="relative h-48 bg-gradient-to-br from-brand-900/50 to-brand-800/30 flex items-center justify-center overflow-hidden">
                            <div class="absolute inset-0 shimmer"></div>
                            <svg xmlns="http://www.w3.org/2000/svg" width="64" height="64" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" class="text-brand-400/30"><path d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M22 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>
                            <div class="absolute top-4 right-4 px-3 py-1 rounded-full bg-brand-500/20 text-brand-400 text-xs font-semibold">ML</div>
                        </div>
                        <div class="p-8">
                            <h3 class="text-2xl font-bold text-white mb-3">Predict Customer Churn</h3>
                            <p class="text-slate-400 mb-6 leading-relaxed">ML model predicting which customers will leave — saving business revenue through proactive retention strategies and data-driven insights.</p>
                            <div class="flex flex-wrap gap-2 mb-6">
                                <span class="px-3 py-1 rounded-full bg-brand-500/10 text-brand-400 text-xs font-medium">Python</span>
                                <span class="px-3 py-1 rounded-full bg-brand-500/10 text-brand-400 text-xs font-medium">Sklearn</span>
                                <span class="px-3 py-1 rounded-full bg-brand-500/10 text-brand-400 text-xs font-medium">Pandas</span>
                                <span class="px-3 py-1 rounded-full bg-brand-500/10 text-brand-400 text-xs font-medium">EDA</span>
                            </div>
                            <div class="flex items-center gap-2 text-brand-400 font-medium group">
                                <span>View Project</span>
                                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="transition-transform group-hover:translate-x-1 group-hover:-translate-y-1"><path d="M7 7h10v10"/><path d="M7 17 17 7"/></svg>
                            </div>
                        </div>
                    </div>
                </a>
            </div>

            <div class="reveal">
                <a href="https://github.com/Sayan-2607/JOB_RECOMM_SYSTEM" target="_blank" class="project-card block gradient-border">
                    <div class="bg-[#111827] rounded-[14px] overflow-hidden">
                        <div class="relative h-48 bg-gradient-to-br from-accent-purple/20 to-accent-purple/5 flex items-center justify-center overflow-hidden">
                            <div class="absolute inset-0 shimmer"></div>
                            <svg xmlns="http://www.w3.org/2000/svg" width="64" height="64" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" class="text-accent-purple/30"><rect width="20" height="14" x="2" y="7" rx="2" ry="2"/><path d="M16 21V5a2 2 0 0 0-2-2h-4a2 2 0 0 0-2 2v16"/></svg>
                            <div class="absolute top-4 right-4 px-3 py-1 rounded-full bg-accent-purple/20 text-accent-purple text-xs font-semibold">NLP</div>
                        </div>
                        <div class="p-8">
                            <h3 class="text-2xl font-bold text-white mb-3">Job Recommendation System</h3>
                            <p class="text-slate-400 mb-6 leading-relaxed">AI engine matching candidates to jobs based on skill analysis using NLP and TF-IDF vectorization for intelligent job-candidate pairing.</p>
                            <div class="flex flex-wrap gap-2 mb-6">
                                <span class="px-3 py-1 rounded-full bg-accent-purple/10 text-accent-purple text-xs font-medium">Python</span>
                                <span class="px-3 py-1 rounded-full bg-accent-purple/10 text-accent-purple text-xs font-medium">NLP</span>
                                <span class="px-3 py-1 rounded-full bg-accent-purple/10 text-accent-purple text-xs font-medium">TF-IDF</span>
                                <span class="px-3 py-1 rounded-full bg-accent-purple/10 text-accent-purple text-xs font-medium">ML</span>
                            </div>
                            <div class="flex items-center gap-2 text-accent-purple font-medium group">
                                <span>View Project</span>
                                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="transition-transform group-hover:translate-x-1 group-hover:-translate-y-1"><path d="M7 7h10v10"/><path d="M7 17 17 7"/></svg>
                            </div>
                        </div>
                    </div>
                </a>
            </div>

            <div class="reveal">
                <a href="https://github.com/Sayan-2607/AI-Sensing-for-Health-" target="_blank" class="project-card block gradient-border">
                    <div class="bg-[#111827] rounded-[14px] overflow-hidden">
                        <div class="relative h-48 bg-gradient-to-br from-accent-teal/20 to-accent-teal/5 flex items-center justify-center overflow-hidden">
                            <div class="absolute inset-0 shimmer"></div>
                            <svg xmlns="http://www.w3.org/2000/svg" width="64" height="64" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" class="text-accent-teal/30"><path d="M19 14c1.49-1.46 3-3.21 3-5.5A5.5 5.5 0 0 0 16.5 3c-1.76 0-3 .5-4.5 2-1.5-1.5-2.74-2-4.5-2A5.5 5.5 0 0 0 2 8.5c0 2.3 1.5 4.05 3 5.5l7 7Z"/></svg>
                            <div class="absolute top-4 right-4 px-3 py-1 rounded-full bg-accent-teal/20 text-accent-teal text-xs font-semibold">Deep Learning</div>
                        </div>
                        <div class="p-8">
                            <h3 class="text-2xl font-bold text-white mb-3">AI Health Sensing</h3>
                            <p class="text-slate-400 mb-6 leading-relaxed">Smart health monitoring using AI sensor fusion and analytics — transforming raw sensor data into actionable health insights.</p>
                            <div class="flex flex-wrap gap-2 mb-6">
                                <span class="px-3 py-1 rounded-full bg-accent-teal/10 text-accent-teal text-xs font-medium">Python</span>
                                <span class="px-3 py-1 rounded-full bg-accent-teal/10 text-accent-teal text-xs font-medium">Deep Learning</span>
                                <span class="px-3 py-1 rounded-full bg-accent-teal/10 text-accent-teal text-xs font-medium">IoT</span>
                                <span class="px-3 py-1 rounded-full bg-accent-teal/10 text-accent-teal text-xs font-medium">Sensors</span>
                            </div>
                            <div class="flex items-center gap-2 text-accent-teal font-medium group">
                                <span>View Project</span>
                                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="transition-transform group-hover:translate-x-1 group-hover:-translate-y-1"><path d="M7 7h10v10"/><path d="M7 17 17 7"/></svg>
                            </div>
                        </div>
                    </div>
                </a>
            </div>

            <div class="reveal">
                <a href="https://github.com/Sayan-2607/FED_KIIT" target="_blank" class="project-card block gradient-border">
                    <div class="bg-[#111827] rounded-[14px] overflow-hidden">
                        <div class="relative h-48 bg-gradient-to-br from-accent-orange/20 to-accent-orange/5 flex items-center justify-center overflow-hidden">
                            <div class="absolute inset-0 shimmer"></div>
                            <svg xmlns="http://www.w3.org/2000/svg" width="64" height="64" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" class="text-accent-orange/30"><rect width="18" height="18" x="3" y="3" rx="2"/><path d="M3 9h18"/><path d="M9 21V9"/></svg>
                            <div class="absolute top-4 right-4 px-3 py-1 rounded-full bg-accent-orange/20 text-accent-orange text-xs font-semibold">Frontend</div>
                        </div>
                        <div class="p-8">
                            <h3 class="text-2xl font-bold text-white mb-3">FED KIIT Platform</h3>
                            <p class="text-slate-400 mb-6 leading-relaxed">Frontend Dev Club portal for KIIT's developer community — a modern, responsive platform connecting developers and resources.</p>
                            <div class="flex flex-wrap gap-2 mb-6">
                                <span class="px-3 py-1 rounded-full bg-accent-orange/10 text-accent-orange text-xs font-medium">HTML</span>
                                <span class="px-3 py-1 rounded-full bg-accent-orange/10 text-accent-orange text-xs font-medium">CSS</span>
                                <span class="px-3 py-1 rounded-full bg-accent-orange/10 text-accent-orange text-xs font-medium">JS</span>
                                <span class="px-3 py-1 rounded-full bg-accent-orange/10 text-accent-orange text-xs font-medium">Responsive</span>
                            </div>
                            <div class="flex items-center gap-2 text-accent-orange font-medium group">
                                <span>View Project</span>
                                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="transition-transform group-hover:translate-x-1 group-hover:-translate-y-1"><path d="M7 7h10v10"/><path d="M7 17 17 7"/></svg>
                            </div>
                        </div>
                    </div>
                </a>
            </div>
        </div>
    </div>
</section>

<!-- STATS SECTION -->
<section id="stats" class="relative py-24 md:py-32">
    <div class="absolute inset-0 bg-gradient-to-b from-transparent via-accent-purple/5 to-transparent"></div>
    <div class="relative max-w-7xl mx-auto px-6">
        <div class="text-center mb-16 reveal">
            <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full glass mb-6">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-brand-400"><path d="M3 3v16a2 2 0 0 0 2 2h16"/><path d="m19 9-5 5-4-4-3 3"/></svg>
                <span class="text-sm font-medium text-slate-300">GitHub Analytics</span>
            </div>
            <h2 class="text-4xl md:text-5xl font-bold font-outfit mb-4">Coding <span class="gradient-text">Journey</span></h2>
        </div>

        <div class="grid grid-cols-2 md:grid-cols-4 gap-6 mb-12 reveal">
            <div class="glass rounded-2xl p-6 text-center hover:border-brand-400/30 transition-all">
                <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-brand-400 mx-auto mb-3"><circle cx="12" cy="12" r="3"/><line x1="3" x2="9" y1="12" y2="12"/><line x1="15" x2="21" y1="12" y2="12"/></svg>
                <p class="text-3xl font-bold text-white stat-number" data-target="500">0</p>
                <p class="text-sm text-slate-400 mt-1">Commits</p>
            </div>
            <div class="glass rounded-2xl p-6 text-center hover:border-accent-purple/30 transition-all">
                <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-accent-purple mx-auto mb-3"><path d="M4 20h16a2 2 0 0 0 2-2V8a2 2 0 0 0-2-2h-7.93a2 2 0 0 1-1.66-.9l-.82-1.2A2 2 0 0 0 7.93 3H4a2 2 0 0 0-2 2v13c0 1.1.9 2 2 2Z"/><path d="M2 10h20"/></svg>
                <p class="text-3xl font-bold text-white stat-number" data-target="25">0</p>
                <p class="text-sm text-slate-400 mt-1">Repositories</p>
            </div>
            <div class="glass rounded-2xl p-6 text-center hover:border-accent-teal/30 transition-all">
                <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-accent-teal mx-auto mb-3"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
                <p class="text-3xl font-bold text-white stat-number" data-target="50">0</p>
                <p class="text-sm text-slate-400 mt-1">Stars Earned</p>
            </div>
            <div class="glass rounded-2xl p-6 text-center hover:border-accent-orange/30 transition-all">
                <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-accent-orange mx-auto mb-3"><path d="M8.5 14.5A2.5 2.5 0 0 0 11 12c0-1.38-.5-2-1-3-1.072-2.143-2.072-2.143-3-2.143-1.928 0-2.928 0-3 2.143-.5 1-1 1.62-1 3a2.5 2.5 0 0 0 2.5 2.5Z"/><path d="M12.5 14.5A2.5 2.5 0 0 0 15 12c0-1.38-.5-2-1-3-1.072-2.143-2.072-2.143-3-2.143-1.928 0-2.928 0-3 2.143-.5 1-1 1.62-1 3a2.5 2.5 0 0 0 2.5 2.5Z"/><path d="M16.5 14.5A2.5 2.5 0 0 0 19 12c0-1.38-.5-2-1-3-1.072-2.143-2.072-2.143-3-2.143-1.928 0-2.928 0-3 2.143-.5 1-1 1.62-1 3a2.5 2.5 0 0 0 2.5 2.5Z"/></svg>
                <p class="text-3xl font-bold text-white stat-number" data-target="365">0</p>
                <p class="text-sm text-slate-400 mt-1">Day Streak</p>
            </div>
        </div>

        <div class="grid md:grid-cols-2 gap-6 mb-8 reveal">
            <div class="glass rounded-2xl p-4 overflow-hidden">
                <img src="https://github-readme-stats.vercel.app/api?username=Sayan-2607&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true&title_color=58A6FF&icon_color=58A6FF&bg_color=0d1117&text_color=c9d1d9&rank_icon=github" 
                     alt="GitHub Stats" class="w-full rounded-xl" loading="lazy">
            </div>
            <div class="glass rounded-2xl p-4 overflow-hidden">
                <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Sayan-2607&layout=compact&langs_count=8&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=58A6FF&text_color=c9d1d9" 
                     alt="Top Languages" class="w-full rounded-xl" loading="lazy">
            </div>
        </div>

        <div class="reveal">
            <div class="glass rounded-2xl p-4 overflow-hidden">
                <img src="https://streak-stats.demolab.com?user=Sayan-2607&theme=tokyonight-duo&hide_border=true&background=0d1117&stroke=58A6FF&ring=58A6FF&fire=FF6B35&currStreakLabel=58A6FF" 
                     alt="GitHub Streak" class="w-full rounded-xl" loading="lazy">
            </div>
        </div>

        <div class="mt-8 reveal">
            <div class="glass rounded-2xl p-6">
                <h3 class="text-xl font-bold text-white mb-4 flex items-center gap-2">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-brand-400"><path d="M22 12h-2.48a2 2 0 0 0-1.93 1.46l-2.35 8.36a.25.25 0 0 1-.48 0L9.24 2.18a.25.25 0 0 0-.48 0l-2.35 8.36A2 2 0 0 1 4.49 12H2"/></svg>
                    Contribution Activity
                </h3>
                <img src="https://github-readme-activity-graph.vercel.app/graph?username=Sayan-2607&theme=tokyo-night&bg_color=0d1117&color=58A6FF&line=58A6FF&point=FF6B35&area=true&hide_border=true&area_color=58A6FF" 
                     alt="Contribution Graph" class="w-full rounded-xl" loading="lazy">
            </div>
        </div>
    </div>
</section>

<!-- TROPHIES SECTION -->
<section class="relative py-16">
    <div class="max-w-7xl mx-auto px-6">
        <div class="reveal">
            <div class="glass rounded-2xl p-6 overflow-hidden">
                <h3 class="text-xl font-bold text-white mb-6 text-center flex items-center justify-center gap-2">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-yellow-400"><path d="M6 9H4.5a2.5 2.5 0 0 1 0-5H6"/><path d="M18 9h1.5a2.5 2.5 0 0 0 0-5H18"/><path d="M4 22h16"/><path d="M10 14.66V17c0 .55-.47.98-.97 1.21C7.85 18.75 7 20.24 7 22"/><path d="M14 14.66V17c0 .55.47.98.97 1.21C16.15 18.75 17 20.24 17 22"/><path d="M18 2H6v7a6 6 0 0 0 12 0V2Z"/></svg>
                    GitHub Trophies
                </h3>
                <img src="https://github-profile-trophy.vercel.app/?username=Sayan-2607&theme=tokyonight&no-frame=true&no-bg=true&margin-w=8&column=7" 
                     alt="GitHub Trophies" class="w-full" loading="lazy">
            </div>
        </div>
    </div>
</section>

<!-- QUOTE SECTION -->
<section class="relative py-24">
    <div class="max-w-4xl mx-auto px-6 text-center reveal">
        <div class="glass rounded-3xl p-12 relative overflow-hidden">
            <div class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-brand-500 via-accent-purple to-accent-orange"></div>
            <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" class="text-brand-400/30 mx-auto mb-6"><path d="M3 21c3 0 7-1 7-8V5c0-1.25-.756-2.017-2-2H4c-1.25 0-2 .75-2 1.972V11c0 1.25.75 2 2 2 1 0 1 0 1 1v1c0 1-1 2-2 2s-1 .008-1 1.031V20c0 1 0 1 1 1z"/><path d="M15 21c3 0 7-1 7-8V5c0-1.25-.757-2.017-2-2h-4c-1.25 0-2 .75-2 1.972V11c0 1.25.75 2 2 2 1 0 1 0 1 1v1c0 1-1 2-2 2s-1 .008-1 1.031V20c0 1 0 1 1 1z"/></svg>
            <blockquote class="text-2xl md:text-3xl font-light text-slate-300 italic leading-relaxed mb-6">
                "The best way to predict the future is to implement it."
            </blockquote>
            <p class="text-brand-400 font-semibold">— David Heinemeier Hansson</p>
        </div>
    </div>
</section>

<!-- CONTACT SECTION -->
<section id="contact" class="relative py-24 md:py-32">
    <div class="absolute inset-0 bg-gradient-to-t from-brand-500/5 to-transparent"></div>
    <div class="relative max-w-7xl mx-auto px-6">
        <div class="text-center mb-16 reveal">
            <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full glass mb-6">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-brand-400"><path d="m22 2-7 20-4-9-9-4Z"/><path d="M22 2 11 13"/></svg>
                <span class="text-sm font-medium text-slate-300">Get In Touch</span>
            </div>
            <h2 class="text-4xl md:text-5xl font-bold font-outfit mb-4">Let's <span class="gradient-text">Build Together</span></h2>
            <p class="text-slate-400 text-lg max-w-2xl mx-auto">Open to internships, research collaborations, and exciting projects. Let's create something amazing.</p>
        </div>

        <div class="grid md:grid-cols-3 gap-6 max-w-4xl mx-auto reveal">
            <a href="https://www.linkedin.com/in/sayan-g-600ab5307/" target="_blank" class="contact-btn glass rounded-2xl p-8 text-center hover:border-[#0A66C2]/50 transition-all group">
                <div class="w-16 h-16 rounded-2xl bg-[#0A66C2]/10 flex items-center justify-center mx-auto mb-4 group-hover:bg-[#0A66C2]/20 transition-all">
                    <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-[#0A66C2]"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect width="4" height="12" x="2" y="9"/><circle cx="4" cy="4" r="2"/></svg>
                </div>
                <h3 class="text-lg font-bold text-white mb-1">LinkedIn</h3>
                <p class="text-sm text-slate-400">Connect with me</p>
            </a>

            <a href="mailto:sayanghosh2607@gmail.com" class="contact-btn glass rounded-2xl p-8 text-center hover:border-[#EA4335]/50 transition-all group">
                <div class="w-16 h-16 rounded-2xl bg-[#EA4335]/10 flex items-center justify-center mx-auto mb-4 group-hover:bg-[#EA4335]/20 transition-all">
                    <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-[#EA4335]"><rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
                </div>
                <h3 class="text-lg font-bold text-white mb-1">Email</h3>
                <p class="text-sm text-slate-400">sayanghosh2607@gmail.com</p>
            </a>

            <a href="https://github.com/Sayan-2607" target="_blank" class="contact-btn glass rounded-2xl p-8 text-center hover:border-white/30 transition-all group">
                <div class="w-16 h-16 rounded-2xl bg-white/5 flex items-center justify-center mx-auto mb-4 group-hover:bg-white/10 transition-all">
                    <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-white"><path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"/><path d="M9 18c-4.51 2-5-2-7-2"/></svg>
                </div>
                <h3 class="text-lg font-bold text-white mb-1">GitHub</h3>
                <p class="text-sm text-slate-400">Follow my work</p>
            </a>
        </div>

        <div class="text-center mt-12 reveal">
            <div class="inline-flex items-center gap-2 px-6 py-3 rounded-full glass">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-accent-rose"><path d="M20 10c0 6-8 12-8 12s-8-6-8-12a8 8 0 0 1 16 0Z"/><circle cx="12" cy="10" r="3"/></svg>
                <span class="text-sm text-slate-300">Based in Bhubaneswar, India</span>
            </div>
        </div>
    </div>
</section>

<!-- FOOTER -->
<footer class="relative py-12 border-t border-slate-800/50">
    <div class="max-w-7xl mx-auto px-6">
        <div class="flex flex-col md:flex-row items-center justify-between gap-6">
            <div class="flex items-center gap-3">
                <div class="w-10 h-10 rounded-xl bg-gradient-to-br from-brand-500 to-brand-600 flex items-center justify-center">
                    <span class="text-lg font-bold text-white">SG</span>
                </div>
                <div>
                    <p class="font-bold text-white">Sayan Ghosh</p>
                    <p class="text-xs text-slate-500">AI Engineer & ML Researcher</p>
                </div>
            </div>

            <div class="flex items-center gap-6">
                <a href="https://github.com/Sayan-2607" target="_blank" class="text-slate-400 hover:text-white transition-colors">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"/><path d="M9 18c-4.51 2-5-2-7-2"/></svg>
                </a>
                <a href="https://www.linkedin.com/in/sayan-g-600ab5307/" target="_blank" class="text-slate-400 hover:text-white transition-colors">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect width="4" height="12" x="2" y="9"/><circle cx="4" cy="4" r="2"/></svg>
                </a>
                <a href="https://www.instagram.com/quantx.exe?igsh=bXJmcHY4dzI5ZHgw" target="_blank" class="text-slate-400 hover:text-white transition-colors">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>
                </a>
                <a href="https://www.instagram.com/quantx.exe?igsh=bXJmcHY4dzI5ZHgw" target="_blank" class="w-12 h-12 rounded-xl glass flex items-center justify-center text-slate-400 hover:text-white hover:border-brand-400/50 transition-all tooltip" data-tooltip="Instagram">
                        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>
                    </a>
                <a href="mailto:sayanghosh2607@gmail.com" class="text-slate-400 hover:text-white transition-colors">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
                </a>
            </div>

            <p class="text-sm text-slate-500">
                &copy; 2026 Sayan Ghosh. Crafted with <span class="text-accent-rose">&#9829;</span> and AI.
            </p>
        </div>
    </div>
</footer>

<!-- SCRIPTS -->
<script>
// ===== PARTICLES BACKGROUND =====
const canvas = document.getElementById('particles-canvas');
const ctx = canvas.getContext('2d');
let particles = [];
let animationId;

function resizeCanvas() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
}
resizeCanvas();
window.addEventListener('resize', resizeCanvas);

class Particle {
    constructor() {
        this.x = Math.random() * canvas.width;
        this.y = Math.random() * canvas.height;
        this.size = Math.random() * 2 + 0.5;
        this.speedX = (Math.random() - 0.5) * 0.5;
        this.speedY = (Math.random() - 0.5) * 0.5;
        this.opacity = Math.random() * 0.5 + 0.1;
    }
    update() {
        this.x += this.speedX;
        this.y += this.speedY;
        if (this.x < 0 || this.x > canvas.width) this.speedX *= -1;
        if (this.y < 0 || this.y > canvas.height) this.speedY *= -1;
    }
    draw() {
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
        ctx.fillStyle = `rgba(13, 138, 242, ${this.opacity})`;
        ctx.fill();
    }
}

function initParticles() {
    particles = [];
    const count = Math.min(80, Math.floor(window.innerWidth / 20));
    for (let i = 0; i < count; i++) {
        particles.push(new Particle());
    }
}
initParticles();

function animateParticles() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    particles.forEach(p => {
        p.update();
        p.draw();
    });

    // Draw connections
    for (let i = 0; i < particles.length; i++) {
        for (let j = i + 1; j < particles.length; j++) {
            const dx = particles[i].x - particles[j].x;
            const dy = particles[i].y - particles[j].y;
            const dist = Math.sqrt(dx * dx + dy * dy);
            if (dist < 150) {
                ctx.beginPath();
                ctx.moveTo(particles[i].x, particles[i].y);
                ctx.lineTo(particles[j].x, particles[j].y);
                ctx.strokeStyle = `rgba(13, 138, 242, ${0.1 * (1 - dist / 150)})`;
                ctx.lineWidth = 0.5;
                ctx.stroke();
            }
        }
    }
    animationId = requestAnimationFrame(animateParticles);
}
animateParticles();

// ===== TYPEWRITER EFFECT =====
const typewriterText = document.getElementById('typewriter');
const phrases = [
    'Building AI that matters',
    'Turning data into decisions',
    'Scalable ML | Real-world impact',
    'Open to Internships & Opportunities'
];
let phraseIndex = 0;
let charIndex = 0;
let isDeleting = false;
let typeSpeed = 100;

function typeWriter() {
    const currentPhrase = phrases[phraseIndex];
    if (isDeleting) {
        typewriterText.textContent = currentPhrase.substring(0, charIndex - 1);
        charIndex--;
        typeSpeed = 50;
    } else {
        typewriterText.textContent = currentPhrase.substring(0, charIndex + 1);
        charIndex++;
        typeSpeed = 100;
    }

    if (!isDeleting && charIndex === currentPhrase.length) {
        isDeleting = true;
        typeSpeed = 2000;
    } else if (isDeleting && charIndex === 0) {
        isDeleting = false;
        phraseIndex = (phraseIndex + 1) % phrases.length;
        typeSpeed = 500;
    }

    setTimeout(typeWriter, typeSpeed);
}
typeWriter();

// ===== GSAP ANIMATIONS =====
gsap.registerPlugin(ScrollTrigger);

// Navbar show on scroll
ScrollTrigger.create({
    start: 'top -100',
    onUpdate: (self) => {
        const navbar = document.getElementById('navbar');
        if (self.direction === -1 || self.progress > 0.05) {
            navbar.classList.remove('opacity-0', '-translate-y-full');
        } else {
            navbar.classList.add('opacity-0', '-translate-y-full');
        }
    }
});

// Hero animations
gsap.from('.hero-badge', { opacity: 0, y: 30, duration: 1, delay: 0.3 });
gsap.from('.hero-title-1', { opacity: 0, x: -50, duration: 1, delay: 0.5 });
gsap.from('.hero-title-2', { opacity: 0, x: 50, duration: 1, delay: 0.7 });
gsap.from('.hero-desc', { opacity: 0, y: 30, duration: 1, delay: 1 });
gsap.from('.hero-buttons', { opacity: 0, y: 30, duration: 1, delay: 1.2 });
gsap.from('.hero-social', { opacity: 0, y: 30, duration: 1, delay: 1.4 });
gsap.from('.hero-visual', { opacity: 0, scale: 0.8, duration: 1.5, delay: 0.8, ease: 'back.out(1.7)' });

// Reveal animations
const revealElements = document.querySelectorAll('.reveal');
revealElements.forEach((el) => {
    gsap.to(el, {
        scrollTrigger: {
            trigger: el,
            start: 'top 85%',
            toggleActions: 'play none none none'
        },
        opacity: 1,
        y: 0,
        duration: 0.8,
        ease: 'power3.out'
    });
});

// Skill bars animation
const skillBars = document.querySelectorAll('.skill-bar');
skillBars.forEach((bar) => {
    const width = bar.getAttribute('data-width');
    gsap.to(bar, {
        scrollTrigger: {
            trigger: bar,
            start: 'top 90%'
        },
        width: width + '%',
        duration: 1.5,
        ease: 'power3.out'
    });
});

// Stat counter animation
const statNumbers = document.querySelectorAll('.stat-number');
statNumbers.forEach((stat) => {
    const target = parseInt(stat.getAttribute('data-target'));
    gsap.to(stat, {
        scrollTrigger: {
            trigger: stat,
            start: 'top 85%'
        },
        innerText: target,
        duration: 2,
        snap: { innerText: 1 },
        ease: 'power2.out'
    });
});

// Mobile menu
const mobileMenuBtn = document.getElementById('mobile-menu-btn');
const mobileMenu = document.getElementById('mobile-menu');
const mobileMenuClose = document.getElementById('mobile-menu-close');
const mobileLinks = document.querySelectorAll('.mobile-link');

mobileMenuBtn.addEventListener('click', () => {
    mobileMenu.classList.remove('hidden');
    mobileMenu.classList.add('flex');
});

mobileMenuClose.addEventListener('click', () => {
    mobileMenu.classList.add('hidden');
    mobileMenu.classList.remove('flex');
});

mobileLinks.forEach(link => {
    link.addEventListener('click', () => {
        mobileMenu.classList.add('hidden');
        mobileMenu.classList.remove('flex');
    });
});

// Smooth scroll for anchor links
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function(e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        if (target) {
            target.scrollIntoView({ behavior: 'smooth', block: 'start' });
        }
    });
});
</script>
</body>
</html>
