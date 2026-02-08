<!-- Global Styles -->
<style>
  @keyframes gradientShift {
    0%, 100% { transform: translate(0, 0) rotate(0deg); }
    33% { transform: translate(30px, -30px) rotate(120deg); }
    66% { transform: translate(-20px, 20px) rotate(240deg); }
  }
  @keyframes pulse {
    0%, 100% { transform: scale(1); box-shadow: 0 0 0 0 rgba(6, 182, 212, 0.4); }
    50% { transform: scale(1.05); box-shadow: 0 0 0 10px rgba(6, 182, 212, 0); }
  }
  @keyframes float {
    0%, 100% { transform: translateY(0px) rotate(0deg); }
    50% { transform: translateY(-20px) rotate(5deg); }
  }
  @keyframes shimmer {
    0% { background-position: -1000px 0; }
    100% { background-position: 1000px 0; }
  }
  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(30px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  @keyframes glow {
    0%, 100% { box-shadow: 0 0 5px rgba(6, 182, 212, 0.3), 0 0 10px rgba(6, 182, 212, 0.2); }
    50% { box-shadow: 0 0 20px rgba(6, 182, 212, 0.5), 0 0 30px rgba(6, 182, 212, 0.3); }
  }

  /* Noise texture overlay */
  .noise-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 9999;
    opacity: 0.03;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 400 400' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)'/%3E%3C/svg%3E");
  }

  .hero-container {
    position: relative;
    padding: 100px 40px 120px;
    background: linear-gradient(135deg, #0f172a 0%, #1e293b 50%, #334155 100%);
    border-radius: 0 0 50% 50% / 40px;
    overflow: hidden;
    margin-bottom: 60px;
  }

  .hero-bg {
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background:
      radial-gradient(circle at 20% 80%, rgba(6, 182, 212, 0.15) 0%, transparent 50%),
      radial-gradient(circle at 80% 20%, rgba(14, 165, 233, 0.15) 0%, transparent 50%),
      radial-gradient(circle at 40% 40%, rgba(16, 185, 129, 0.1) 0%, transparent 50%),
      radial-gradient(circle at 60% 60%, rgba(245, 158, 11, 0.08) 0%, transparent 40%);
    animation: gradientShift 20s ease infinite;
    pointer-events: none;
  }

  /* Floating decorative shapes */
  .hero-shape {
    position: absolute;
    border-radius: 50%;
    filter: blur(60px);
    opacity: 0.4;
    animation: float 8s ease-in-out infinite;
  }
  .hero-shape-1 {
    width: 300px;
    height: 300px;
    background: linear-gradient(135deg, #06b6d4, #0ea5e9);
    top: 10%;
    left: 10%;
    animation-delay: 0s;
  }
  .hero-shape-2 {
    width: 200px;
    height: 200px;
    background: linear-gradient(135deg, #10b981, #14b8a6);
    top: 60%;
    right: 15%;
    animation-delay: 2s;
  }
  .hero-shape-3 {
    width: 150px;
    height: 150px;
    background: linear-gradient(135deg, #f59e0b, #f97316);
    bottom: 20%;
    left: 20%;
    animation-delay: 4s;
  }

  .hero-content {
    position: relative;
    z-index: 1;
    animation: fadeInUp 1s ease-out;
  }

  .hero-badge {
    display: inline-block;
    padding: 10px 24px;
    background: linear-gradient(135deg, #06b6d4, #0ea5e9);
    border-radius: 50px;
    margin-bottom: 24px;
    animation: pulse 2s ease-in-out infinite, glow 3s ease-in-out infinite;
    box-shadow: 0 4px 15px rgba(6, 182, 212, 0.3);
  }

  .hero-title {
    font-size: 64px;
    font-weight: 800;
    background: linear-gradient(135deg, #fff 0%, #67e8f9 30%, #7dd3fc 50%, #67e8f9 70%, #fff 100%);
    background-size: 200% auto;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin: 20px 0;
    letter-spacing: -3px;
    animation: shimmer 4s linear infinite;
  }

  .hero-subtitle {
    font-size: 20px;
    color: #cbd5e1;
    margin: 0 0 30px;
    font-weight: 300;
    max-width: 600px;
    line-height: 1.7;
  }

  .social-link {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    padding: 14px 28px;
    background: rgba(6, 182, 212, 0.1);
    border: 2px solid rgba(6, 182, 212, 0.3);
    border-radius: 16px;
    color: #22d3ee;
    text-decoration: none;
    font-weight: 600;
    font-size: 14px;
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    backdrop-filter: blur(10px);
    position: relative;
    overflow: hidden;
  }

  .social-link::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(6, 182, 212, 0.2), transparent);
    transition: left 0.5s;
  }

  .social-link:hover::before {
    left: 100%;
  }

  .social-link:hover {
    transform: translateY(-4px) scale(1.02);
    box-shadow: 0 12px 35px rgba(6, 182, 212, 0.4);
    border-color: rgba(6, 182, 212, 0.6);
    background: rgba(6, 182, 212, 0.15);
  }
</style>

<div class="noise-overlay"></div>

<div align="center">

<!-- Hero Section with Enhanced Visual Effects -->
<div class="hero-container">

  <!-- Animated Background Elements -->
  <div class="hero-bg"></div>

  <!-- Floating Decorative Shapes -->
  <div class="hero-shape hero-shape-1"></div>
  <div class="hero-shape hero-shape-2"></div>
  <div class="hero-shape hero-shape-3"></div>

  <!-- Content -->
  <div class="hero-content">
    <div class="hero-badge">
      <span style="color: white; font-size: 13px; font-weight: 700; letter-spacing: 2.5px; text-transform: uppercase;">PhD Candidate</span>
    </div>

    <h1 class="hero-title">
      Dizhan Xue
    </h1>

    <p class="hero-subtitle">
      PhD Candidate @ <span style="color: #22d3ee; font-weight: 600;">State Key Laboratory of Multimodal Artificial Intelligence Systems</span>
      <br>
      <span style="color: #94a3b8; font-size: 18px;">Institute of Automation, Chinese Academy of Sciences</span>
    </p>

    <!-- Social Links -->
    <div style="display: flex; gap: 14px; justify-content: center; flex-wrap: wrap; margin-top: 20px;">
      <a href="mailto:xuedizhan17@mails.ucas.ac.cn" class="social-link">
        📧 Email
      </a>
      <a href="https://scholar.google.com/citations?user=0000000000" class="social-link">
        🎓 Google Scholar
      </a>
      <a href="https://dblp.org/pid/293/9621" class="social-link">
        📚 DBLP
      </a>
      <a href="https://github.com/LivXue" class="social-link">
        💻 GitHub
      </a>
    </div>
  </div>
</div>

</div>

<!-- Custom Divider -->
<div style="display: flex; align-items: center; justify-content: center; gap: 20px; margin: 60px 0; opacity: 0.6;">
  <div style="flex: 1; height: 1px; background: linear-gradient(90deg, transparent, #06b6d4, transparent);"></div>
  <div style="width: 8px; height: 8px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); border-radius: 50%;"></div>
  <div style="flex: 1; height: 1px; background: linear-gradient(90deg, transparent, #06b6d4, transparent);"></div>
</div>


<div style="text-align: center; margin: 80px 0 60px;">
  <div style="display: inline-flex; align-items: center; gap: 16px; padding: 12px 32px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.1) 0%, rgba(14, 165, 233, 0.05) 100%); border: 2px solid rgba(6, 182, 212, 0.2); border-radius: 50px; backdrop-filter: blur(10px);">
    <span style="font-size: 32px; filter: drop-shadow(0 0 10px rgba(6, 182, 212, 0.5));">🎯</span>
    <h2 style="margin: 0; font-size: 28px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; font-weight: 800; letter-spacing: -1px; text-decoration: none !important; border: none !important; border-bottom: none !important; box-shadow: none !important; outline: none !important;">About Me</h2>
  </div>
</div>

<div style="max-width: 800px; margin: 0 auto; padding: 0 20px;">
  <p style="font-size: 17px; line-height: 1.8; color: #cbd5e1; margin-bottom: 24px;">
    I'm a PhD candidate at the <strong style="color: #22d3ee; font-weight: 600;">State Key Laboratory of Multimodal Artificial Intelligence Systems, Institute of Automation, Chinese Academy of Sciences (CASIA)</strong>, advised by Prof. Changsheng Xu.
  </p>

  <div style="padding: 28px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.08) 0%, rgba(14, 165, 233, 0.04) 100%); border: 1px solid rgba(6, 182, 212, 0.2); border-radius: 20px; margin-bottom: 24px;">
    <h3 style="margin: 0 0 16px; color: #22d3ee; font-size: 18px; font-weight: 700; display: flex; align-items: center; gap: 10px;">
      <span>💡</span> My Research Vision
    </h3>
    <p style="margin: 0; color: #cbd5e1; font-size: 16px; line-height: 1.7;">
      My core research focuses on enabling AI to better understand and reason about complex multimodal information. I believe that <strong style="color: #22d3ee; font-weight: 600;">multimodal intelligence is the essential pathway to AGI</strong>. Recently, I've been particularly interested in <strong style="color: #22d3ee; font-weight: 600;">LLM Agents</strong> and their capabilities in sophisticated reasoning tasks.
    </p>
  </div>

  <div style="padding: 28px; background: linear-gradient(135deg, rgba(16, 185, 129, 0.08) 0%, rgba(5, 150, 105, 0.04) 100%); border: 1px solid rgba(16, 185, 129, 0.2); border-radius: 20px; margin-bottom: 24px;">
    <h3 style="margin: 0 0 16px; color: #10b981; font-size: 18px; font-weight: 700; display: flex; align-items: center; gap: 10px;">
      <span>🧠</span> Research Philosophy
    </h3>
    <blockquote style="margin: 0; color: #cbd5e1; font-size: 16px; line-height: 1.8; border-left: 4px solid #10b981; padding-left: 20px; font-style: italic;">
      "True intelligence lies not just in perception, but in reasoning across modalities to construct meaningful understanding."
    </blockquote>
  </div>

  <p style="font-size: 16px; line-height: 1.8; color: #cbd5e1; margin: 0;">
    I'm passionate about building AI systems that can explain their reasoning process because I believe <strong style="color: #22d3ee; font-weight: 600;">interpretability is crucial for trustworthy AI</strong>.
  </p>
</div>

<!-- Custom Divider -->
<div style="display: flex; align-items: center; justify-content: center; gap: 20px; margin: 80px 0; opacity: 0.6;">
  <div style="flex: 1; max-width: 200px; height: 1px; background: linear-gradient(90deg, transparent, #10b981, transparent);"></div>
  <div style="width: 8px; height: 8px; background: linear-gradient(135deg, #10b981, #14b8a6); border-radius: 50%;"></div>
  <div style="flex: 1; max-width: 200px; height: 1px; background: linear-gradient(90deg, transparent, #10b981, transparent);"></div>
</div>

<div style="text-align: center; margin: 80px 0 60px;">
  <div style="display: inline-flex; align-items: center; gap: 16px; padding: 12px 32px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.1) 0%, rgba(14, 165, 233, 0.05) 100%); border: 2px solid rgba(6, 182, 212, 0.2); border-radius: 50px; backdrop-filter: blur(10px);">
    <span style="font-size: 32px; filter: drop-shadow(0 0 10px rgba(6, 182, 212, 0.5));">🎓</span>
    <h2 style="margin: 0; font-size: 28px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; font-weight: 800; letter-spacing: -1px; text-decoration: none !important; border: none !important; border-bottom: none !important; box-shadow: none !important; outline: none !important;">Education</h2>
  </div>
</div>

<div style="display: grid; gap: 24px; margin: 30px 0;">

<!-- PhD -->
<div style="position: relative; padding: 28px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.08) 0%, rgba(14, 165, 233, 0.08) 100%); border: 2px solid rgba(6, 182, 212, 0.25); border-radius: 20px; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden;">
  <div style="position: absolute; top: 0; right: 0; width: 200px; height: 200px; background: radial-gradient(circle, rgba(6, 182, 212, 0.1) 0%, transparent 70%); filter: blur(40px);"></div>

  <div style="position: absolute; top: 20px; right: 20px;">
    <span style="padding: 8px 18px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); color: white; font-size: 11px; font-weight: 700; letter-spacing: 1.5px; border-radius: 25px; text-transform: uppercase; box-shadow: 0 4px 15px rgba(6, 182, 212, 0.3);">Current</span>
  </div>

  <div style="position: relative; z-index: 1; display: flex; align-items: flex-start; gap: 18px; margin-bottom: 16px;">
    <div style="font-size: 40px; filter: drop-shadow(0 4px 8px rgba(6, 182, 212, 0.3));">🔬</div>
    <div style="flex: 1;">
      <h3 style="margin: 0 0 10px; font-size: 20px; color: #e2e8f0; font-weight: 700;">PhD in Pattern Recognition and Intelligent Systems</h3>
      <p style="margin: 0; color: #0891b2; font-size: 15px; font-weight: 500;">Institute of Automation, Chinese Academy of Sciences (CASIA)</p>
    </div>
  </div>

  <div style="position: relative; z-index: 1; margin: 18px 0; padding: 14px 18px; background: rgba(15, 23, 42, 0.6); border-radius: 12px; border: 1px solid rgba(6, 182, 212, 0.2);">
    <p style="margin: 0; color: #94a3b8; font-size: 13px; line-height: 1.8;">
      <span style="color: #06b6d4; font-weight: 700;">📅 Sep 2021 - Jun 2026</span><br>
      <span style="color: #e2e8f0; font-weight: 600;">👨‍🏫 Supervisor:</span> <span style="color: #cbd5e1;">Prof. Changsheng Xu</span><br>
      <span style="color: #e2e8f0; font-weight: 600;">📝 Thesis:</span> <span style="color: #cbd5e1;">Reliable Multimodal Reasoning in Complicated Scenarios</span>
    </p>
  </div>
</div>

<!-- Bachelor -->
<div style="position: relative; padding: 28px; background: linear-gradient(135deg, rgba(16, 185, 129, 0.08) 0%, rgba(5, 150, 105, 0.08) 100%); border: 2px solid rgba(16, 185, 129, 0.25); border-radius: 20px; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden;">
  <div style="position: absolute; top: 0; right: 0; width: 200px; height: 200px; background: radial-gradient(circle, rgba(16, 185, 129, 0.1) 0%, transparent 70%); filter: blur(40px);"></div>

  <div style="position: relative; z-index: 1; display: flex; align-items: flex-start; gap: 18px; margin-bottom: 16px;">
    <div style="font-size: 40px; filter: drop-shadow(0 4px 8px rgba(16, 185, 129, 0.3));">🎓</div>
    <div style="flex: 1;">
      <h3 style="margin: 0 0 10px; font-size: 20px; color: #e2e8f0; font-weight: 700;">Bachelor of Computer Science and Technology</h3>
      <p style="margin: 0; color: #059669; font-size: 15px; font-weight: 500;">University of Chinese Academy of Sciences (UCAS)</p>
    </div>
  </div>

  <div style="position: relative; z-index: 1; margin: 18px 0; padding: 14px 18px; background: rgba(15, 23, 42, 0.6); border-radius: 12px; border: 1px solid rgba(16, 185, 129, 0.2);">
    <p style="margin: 0; color: #94a3b8; font-size: 13px; line-height: 1.8;">
      <span style="color: #10b981; font-weight: 700;">📅 Sep 2017 - Jun 2021</span><br>
      <span style="color: #e2e8f0; font-weight: 600;">👨‍🏫 Supervisor:</span> <span style="color: #cbd5e1;">Prof. Changsheng Xu</span><br>
      <span style="color: #e2e8f0; font-weight: 600;">📝 Thesis:</span> <span style="color: #cbd5e1;">Debiased Short Video Recommendation Based on Counterfactual Reasoning</span>
    </p>
  </div>
</div>

</div>

<!-- Custom Divider -->
<div style="display: flex; align-items: center; justify-content: center; gap: 20px; margin: 80px 0; opacity: 0.6;">
  <div style="flex: 1; max-width: 200px; height: 1px; background: linear-gradient(90deg, transparent, #0ea5e9, transparent);"></div>
  <div style="width: 8px; height: 8px; background: linear-gradient(135deg, #0ea5e9, #06b6d4); border-radius: 50%;"></div>
  <div style="flex: 1; max-width: 200px; height: 1px; background: linear-gradient(90deg, transparent, #0ea5e9, transparent);"></div>
</div>


<div style="text-align: center; margin: 80px 0 60px;">
  <div style="display: inline-flex; align-items: center; gap: 16px; padding: 12px 32px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.1) 0%, rgba(14, 165, 233, 0.05) 100%); border: 2px solid rgba(6, 182, 212, 0.2); border-radius: 50px; backdrop-filter: blur(10px);">
    <span style="font-size: 32px; filter: drop-shadow(0 0 10px rgba(6, 182, 212, 0.5));">🧑‍🔬</span>
    <h2 style="margin: 0; font-size: 28px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; font-weight: 800; letter-spacing: -1px; text-decoration: none !important; border: none !important; border-bottom: none !important; box-shadow: none !important; outline: none !important;">Research Interests</h2>
  </div>
</div>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 20px; margin: 30px 0;">

<div style="position: relative; padding: 32px 28px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.12) 0%, rgba(6, 182, 212, 0.05) 100%); border: 2px solid rgba(6, 182, 212, 0.25); border-radius: 20px; text-align: center; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden; cursor: pointer;">
  <div style="position: absolute; top: 0; right: 0; width: 150px; height: 150px; background: radial-gradient(circle, rgba(6, 182, 212, 0.15) 0%, transparent 70%); filter: blur(30px); opacity: 0; transition: opacity 0.4s ease;"></div>
  <div style="font-size: 48px; margin-bottom: 16px; filter: drop-shadow(0 4px 8px rgba(6, 182, 212, 0.3)); transition: transform 0.4s ease;">🧩</div>
  <h4 style="margin: 0 0 10px; color: #22d3ee; font-size: 18px; font-weight: 700;">Multimodal Reasoning</h4>
  <p style="margin: 0; color: #cbd5e1; font-size: 14px; font-weight: 500;">& Explainable AI</p>
  <style>
    div[style*="cursor: pointer"]:hover {
      transform: translateY(-8px);
      box-shadow: 0 20px 40px rgba(6, 182, 212, 0.3);
      border-color: rgba(6, 182, 212, 0.5);
    }
    div[style*="cursor: pointer"]:hover div[style*="opacity: 0"] {
      opacity: 1;
    }
    div[style*="cursor: pointer"]:hover div[style*="transition: transform"] {
      transform: scale(1.1) rotate(5deg);
    }
  </style>
</div>

<div style="position: relative; padding: 32px 28px; background: linear-gradient(135deg, rgba(14, 165, 233, 0.12) 0%, rgba(14, 165, 233, 0.05) 100%); border: 2px solid rgba(14, 165, 233, 0.25); border-radius: 20px; text-align: center; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden; cursor: pointer;">
  <div style="position: absolute; top: 0; right: 0; width: 150px; height: 150px; background: radial-gradient(circle, rgba(14, 165, 233, 0.15) 0%, transparent 70%); filter: blur(30px); opacity: 0; transition: opacity 0.4s ease;"></div>
  <div style="font-size: 48px; margin-bottom: 16px; filter: drop-shadow(0 4px 8px rgba(14, 165, 233, 0.3)); transition: transform 0.4s ease;">🌐</div>
  <h4 style="margin: 0 0 10px; color: #38bdf8; font-size: 18px; font-weight: 700;">Multimodal LLMs</h4>
  <p style="margin: 0; color: #cbd5e1; font-size: 14px; font-weight: 500;">Vision-Language Models</p>
</div>

<div style="position: relative; padding: 32px 28px; background: linear-gradient(135deg, rgba(16, 185, 129, 0.12) 0%, rgba(16, 185, 129, 0.05) 100%); border: 2px solid rgba(16, 185, 129, 0.25); border-radius: 20px; text-align: center; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden; cursor: pointer;">
  <div style="position: absolute; top: 0; right: 0; width: 150px; height: 150px; background: radial-gradient(circle, rgba(16, 185, 129, 0.15) 0%, transparent 70%); filter: blur(30px); opacity: 0; transition: opacity 0.4s ease;"></div>
  <div style="font-size: 48px; margin-bottom: 16px; filter: drop-shadow(0 4px 8px rgba(16, 185, 129, 0.3)); transition: transform 0.4s ease;">🔄</div>
  <h4 style="margin: 0 0 10px; color: #34d399; font-size: 18px; font-weight: 700;">LLM Agents</h4>
  <p style="margin: 0; color: #cbd5e1; font-size: 14px; font-weight: 500;">& Autonomous Systems</p>
</div>

</div>

<!-- Custom Divider -->
<div style="display: flex; align-items: center; justify-content: center; gap: 20px; margin: 80px 0; opacity: 0.6;">
  <div style="flex: 1; max-width: 200px; height: 1px; background: linear-gradient(90deg, transparent, #10b981, transparent);"></div>
  <div style="width: 8px; height: 8px; background: linear-gradient(135deg, #10b981, #14b8a6); border-radius: 50%;"></div>
  <div style="flex: 1; max-width: 200px; height: 1px; background: linear-gradient(90deg, transparent, #10b981, transparent);"></div>
</div>


<div style="text-align: center; margin: 80px 0 60px;">
  <div style="display: inline-flex; align-items: center; gap: 16px; padding: 12px 32px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.1) 0%, rgba(14, 165, 233, 0.05) 100%); border: 2px solid rgba(6, 182, 212, 0.2); border-radius: 50px; backdrop-filter: blur(10px);">
    <span style="font-size: 32px; filter: drop-shadow(0 0 10px rgba(6, 182, 212, 0.5));">📚</span>
    <h2 style="margin: 0; font-size: 28px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; font-weight: 800; letter-spacing: -1px; text-decoration: none !important; border: none !important; border-bottom: none !important; box-shadow: none !important; outline: none !important;">Publications</h2>
  </div>
</div>

<div style="text-align: center; margin: 50px 0 40px;">
  <h3 style="display: inline-flex; align-items: center; gap: 12px; margin: 0; padding: 10px 24px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.1) 0%, rgba(14, 165, 233, 0.05) 100%); border: 2px solid rgba(6, 182, 212, 0.2); border-radius: 30px; font-size: 20px; color: #22d3ee; font-weight: 700;">
    📖 First-author Papers
  </h3>
</div>

<div style="display: grid; gap: 18px; margin: 20px 0;">

<div style="position: relative; padding: 24px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.1) 0%, rgba(6, 182, 212, 0.04) 100%); border-left: 4px solid #06b6d4; border-radius: 0 16px 16px 0; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden;">
  <div style="position: absolute; top: 0; right: 0; width: 150px; height: 150px; background: radial-gradient(circle, rgba(6, 182, 212, 0.08) 0%, transparent 70%); filter: blur(30px); opacity: 0.5;"></div>
  <div style="position: relative; z-index: 1; display: flex; justify-content: space-between; align-items: flex-start; gap: 16px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0 0 10px; color: #f8fafc; font-size: 16px; line-height: 1.7; font-weight: 500;">
        <strong style="color: #0891b2; font-weight: 700;">Dizhan Xue</strong>, Shengsheng Qian, Changsheng Xu. <em style="color: #0891b2 !important;">Integrating Neural-Symbolic Reasoning With Variational Causal Inference Network for Explanatory Visual Question Answering.</em>
      </p>
      <div style="display: flex; flex-wrap: wrap; gap: 8px; margin-top: 8px;">
        <span style="padding: 4px 12px; background: rgba(6, 182, 212, 0.15); color: #22d3ee; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(6, 182, 212, 0.25);">VQA</span>
        <span style="padding: 4px 12px; background: rgba(6, 182, 212, 0.15); color: #22d3ee; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(6, 182, 212, 0.25);">Causal Inference</span>
        <span style="padding: 4px 12px; background: rgba(6, 182, 212, 0.15); color: #22d3ee; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(6, 182, 212, 0.25);">Explainable AI</span>
        <span style="padding: 4px 12px; background: rgba(6, 182, 212, 0.15); color: #22d3ee; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(6, 182, 212, 0.25);">Neural-Symbolic</span>
      </div>
    </div>
    <span style="padding: 8px 18px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); color: white; font-size: 12px; font-weight: 700; border-radius: 25px; white-space: nowrap; box-shadow: 0 4px 15px rgba(6, 182, 212, 0.3);">IEEE TPAMI 2024</span>
  </div>
</div>

<div style="position: relative; padding: 24px; background: linear-gradient(135deg, rgba(14, 165, 233, 0.1) 0%, rgba(14, 165, 233, 0.04) 100%); border-left: 4px solid #0ea5e9; border-radius: 0 16px 16px 0; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden;">
  <div style="position: absolute; top: 0; right: 0; width: 150px; height: 150px; background: radial-gradient(circle, rgba(14, 165, 233, 0.08) 0%, transparent 70%); filter: blur(30px); opacity: 0.5;"></div>
  <div style="position: relative; z-index: 1; display: flex; justify-content: space-between; align-items: flex-start; gap: 16px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0 0 10px; color: #f8fafc; font-size: 16px; line-height: 1.7; font-weight: 500;">
        <strong style="color: #0284c7; font-weight: 700;">Dizhan Xue</strong>, Jing Cui, Shengsheng Qian, Chuanrui Hu, Changsheng Xu. <em style="color: #0284c7 !important;">SoMe: A Realistic Benchmark for LLM-based Social Media Agents.</em>
      </p>
      <div style="display: flex; flex-wrap: wrap; gap: 8px; margin-top: 8px;">
        <span style="padding: 4px 12px; background: rgba(14, 165, 233, 0.15); color: #38bdf8; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(14, 165, 233, 0.25);">LLM Agents</span>
        <span style="padding: 4px 12px; background: rgba(14, 165, 233, 0.15); color: #38bdf8; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(14, 165, 233, 0.25);">Social Media</span>
        <span style="padding: 4px 12px; background: rgba(14, 165, 233, 0.15); color: #38bdf8; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(14, 165, 233, 0.25);">Benchmark</span>
      </div>
    </div>
    <span style="padding: 8px 18px; background: linear-gradient(135deg, #0ea5e9, #06b6d4); color: white; font-size: 12px; font-weight: 700; border-radius: 25px; white-space: nowrap; box-shadow: 0 4px 15px rgba(14, 165, 233, 0.3);">AAAI 2026</span>
  </div>
</div>

<div style="position: relative; padding: 24px; background: linear-gradient(135deg, rgba(16, 185, 129, 0.1) 0%, rgba(16, 185, 129, 0.04) 100%); border-left: 4px solid #10b981; border-radius: 0 16px 16px 0; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden;">
  <div style="position: absolute; top: 0; right: 0; width: 150px; height: 150px; background: radial-gradient(circle, rgba(16, 185, 129, 0.08) 0%, transparent 70%); filter: blur(30px); opacity: 0.5;"></div>
  <div style="position: relative; z-index: 1; display: flex; justify-content: space-between; align-items: flex-start; gap: 16px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0 0 10px; color: #f8fafc; font-size: 16px; line-height: 1.7; font-weight: 500;">
        <strong style="color: #059669; font-weight: 700;">Dizhan Xue</strong>, Shengsheng Qian, Changsheng Xu. <em style="color: #059669 !important;">Variational Causal Inference Network for Explanatory Visual Question Answering.</em>
      </p>
      <div style="display: flex; flex-wrap: wrap; gap: 8px; margin-top: 8px;">
        <span style="padding: 4px 12px; background: rgba(16, 185, 129, 0.15); color: #34d399; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(16, 185, 129, 0.25);">VQA</span>
        <span style="padding: 4px 12px; background: rgba(16, 185, 129, 0.15); color: #34d399; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(16, 185, 129, 0.25);">Causal Inference</span>
        <span style="padding: 4px 12px; background: rgba(16, 185, 129, 0.15); color: #34d399; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(16, 185, 129, 0.25);">Explainable AI</span>
      </div>
    </div>
    <span style="padding: 8px 18px; background: linear-gradient(135deg, #10b981, #14b8a6); color: white; font-size: 12px; font-weight: 700; border-radius: 25px; white-space: nowrap; box-shadow: 0 4px 15px rgba(16, 185, 129, 0.3);">ICCV 2023</span>
  </div>
</div>

<div style="position: relative; padding: 24px; background: linear-gradient(135deg, rgba(245, 158, 11, 0.1) 0%, rgba(245, 158, 11, 0.04) 100%); border-left: 4px solid #f59e0b; border-radius: 0 16px 16px 0; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden;">
  <div style="position: absolute; top: 0; right: 0; width: 150px; height: 150px; background: radial-gradient(circle, rgba(245, 158, 11, 0.08) 0%, transparent 70%); filter: blur(30px); opacity: 0.5;"></div>
  <div style="position: relative; z-index: 1; display: flex; justify-content: space-between; align-items: flex-start; gap: 16px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0 0 10px; color: #f8fafc; font-size: 16px; line-height: 1.7; font-weight: 500;">
        <strong style="color: #d97706; font-weight: 700;">Dizhan Xue</strong>, Shengsheng Qian, Changsheng Xu. <em style="color: #d97706 !important;">Few-Shot Multimodal Explanation for Visual Question Answering.</em>
      </p>
      <div style="display: flex; flex-wrap: wrap; gap: 8px; margin-top: 8px;">
        <span style="padding: 4px 12px; background: rgba(245, 158, 11, 0.15); color: #fbbf24; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(245, 158, 11, 0.25);">VQA</span>
        <span style="padding: 4px 12px; background: rgba(245, 158, 11, 0.15); color: #fbbf24; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(245, 158, 11, 0.25);">Few-Shot</span>
        <span style="padding: 4px 12px; background: rgba(245, 158, 11, 0.15); color: #fbbf24; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(245, 158, 11, 0.25);">Explainable AI</span>
        <span style="padding: 4px 12px; background: rgba(245, 158, 11, 0.15); color: #fbbf24; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(245, 158, 11, 0.25);">LLM Agents</span>
      </div>
    </div>
    <span style="padding: 8px 18px; background: linear-gradient(135deg, #f59e0b, #f97316); color: white; font-size: 12px; font-weight: 700; border-radius: 25px; white-space: nowrap; box-shadow: 0 4px 15px rgba(245, 158, 11, 0.3);">ACM MM 2024</span>
  </div>
</div>

<div style="position: relative; padding: 24px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.1) 0%, rgba(6, 182, 212, 0.04) 100%); border-left: 4px solid #06b6d4; border-radius: 0 16px 16px 0; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden;">
  <div style="position: absolute; top: 0; right: 0; width: 150px; height: 150px; background: radial-gradient(circle, rgba(6, 182, 212, 0.08) 0%, transparent 70%); filter: blur(30px); opacity: 0.5;"></div>
  <div style="position: relative; z-index: 1; display: flex; justify-content: space-between; align-items: flex-start; gap: 16px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0 0 10px; color: #f8fafc; font-size: 16px; line-height: 1.7; font-weight: 500;">
        <strong style="color: #0891b2; font-weight: 700;">Dizhan Xue</strong>, Shengsheng Qian, Quan Fang, Changsheng Xu. <em style="color: #0891b2 !important;">MMT: Image-guided Story Ending Generation with Multimodal Memory Transformer.</em>
      </p>
      <div style="display: flex; flex-wrap: wrap; gap: 8px; margin-top: 8px;">
        <span style="padding: 4px 12px; background: rgba(6, 182, 212, 0.15); color: #22d3ee; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(6, 182, 212, 0.25);">Cross-Modal Generation</span>
        <span style="padding: 4px 12px; background: rgba(6, 182, 212, 0.15); color: #22d3ee; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(6, 182, 212, 0.25);">Vision-Language</span>
        <span style="padding: 4px 12px; background: rgba(6, 182, 212, 0.15); color: #22d3ee; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(6, 182, 212, 0.25);">Memory</span>
      </div>
    </div>
    <span style="padding: 8px 18px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); color: white; font-size: 12px; font-weight: 700; border-radius: 25px; white-space: nowrap; box-shadow: 0 4px 15px rgba(6, 182, 212, 0.3);">ACM MM 2022</span>
  </div>
</div>

<div style="position: relative; padding: 24px; background: linear-gradient(135deg, rgba(14, 165, 233, 0.1) 0%, rgba(14, 165, 233, 0.04) 100%); border-left: 4px solid #0ea5e9; border-radius: 0 16px 16px 0; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden;">
  <div style="position: absolute; top: 0; right: 0; width: 150px; height: 150px; background: radial-gradient(circle, rgba(14, 165, 233, 0.08) 0%, transparent 70%); filter: blur(30px); opacity: 0.5;"></div>
  <div style="position: relative; z-index: 1; display: flex; justify-content: space-between; align-items: flex-start; gap: 16px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0 0 10px; color: #f8fafc; font-size: 16px; line-height: 1.7; font-weight: 500;">
        <strong style="color: #0284c7; font-weight: 700;">Dizhan Xue</strong>, Shengsheng Qian, Xueshan Deng, Changsheng Xu. <em style="color: #0284c7 !important;">A Unified Framework for Backdoor Trigger Segmentation.</em>
      </p>
      <div style="display: flex; flex-wrap: wrap; gap: 8px; margin-top: 8px;">
        <span style="padding: 4px 12px; background: rgba(14, 165, 233, 0.15); color: #38bdf8; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(14, 165, 233, 0.25);">Backdoor Attack</span>
        <span style="padding: 4px 12px; background: rgba(14, 165, 233, 0.15); color: #38bdf8; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(14, 165, 233, 0.25);">Backdoor Defense</span>
        <span style="padding: 4px 12px; background: rgba(14, 165, 233, 0.15); color: #38bdf8; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(14, 165, 233, 0.25);">AI Security</span>
      </div>
    </div>
    <span style="padding: 8px 18px; background: linear-gradient(135deg, #0ea5e9, #06b6d4); color: white; font-size: 12px; font-weight: 700; border-radius: 25px; white-space: nowrap; box-shadow: 0 4px 15px rgba(14, 165, 233, 0.3);">IEEE TIP (accepted)</span>
  </div>
</div>

<div style="position: relative; padding: 24px; background: linear-gradient(135deg, rgba(16, 185, 129, 0.1) 0%, rgba(16, 185, 129, 0.04) 100%); border-left: 4px solid #10b981; border-radius: 0 16px 16px 0; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden;">
  <div style="position: absolute; top: 0; right: 0; width: 150px; height: 150px; background: radial-gradient(circle, rgba(16, 185, 129, 0.08) 0%, transparent 70%); filter: blur(30px); opacity: 0.5;"></div>
  <div style="position: relative; z-index: 1; display: flex; justify-content: space-between; align-items: flex-start; gap: 16px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0 0 10px; color: #f8fafc; font-size: 16px; line-height: 1.7; font-weight: 500;">
        <strong style="color: #059669; font-weight: 700;">Dizhan Xue</strong>, Shengsheng Qian, Quan Fang, Changsheng Xu. <em style="color: #059669 !important;">LININ: Logic Integrated Neural Inference Network for Explanatory Visual Question Answering.</em>
      </p>
      <div style="display: flex; flex-wrap: wrap; gap: 8px; margin-top: 8px;">
        <span style="padding: 4px 12px; background: rgba(16, 185, 129, 0.15); color: #34d399; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(16, 185, 129, 0.25);">VQA</span>
        <span style="padding: 4px 12px; background: rgba(16, 185, 129, 0.15); color: #34d399; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(16, 185, 129, 0.25);">Neural-Symbolic</span>
        <span style="padding: 4px 12px; background: rgba(16, 185, 129, 0.15); color: #34d399; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(16, 185, 129, 0.25);">Explainable AI</span>
      </div>
    </div>
    <span style="padding: 8px 18px; background: linear-gradient(135deg, #10b981, #14b8a6); color: white; font-size: 12px; font-weight: 700; border-radius: 25px; white-space: nowrap; box-shadow: 0 4px 15px rgba(16, 185, 129, 0.3);">IEEE TMM 2024</span>
  </div>
</div>

<div style="position: relative; padding: 24px; background: linear-gradient(135deg, rgba(245, 158, 11, 0.1) 0%, rgba(245, 158, 11, 0.04) 100%); border-left: 4px solid #f59e0b; border-radius: 0 16px 16px 0; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden;">
  <div style="position: absolute; top: 0; right: 0; width: 150px; height: 150px; background: radial-gradient(circle, rgba(245, 158, 11, 0.08) 0%, transparent 70%); filter: blur(30px); opacity: 0.5;"></div>
  <div style="position: relative; z-index: 1; display: flex; justify-content: space-between; align-items: flex-start; gap: 16px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0 0 10px; color: #f8fafc; font-size: 16px; line-height: 1.7; font-weight: 500;">
        <strong style="color: #d97706; font-weight: 700;">Dizhan Xue</strong>, Shengsheng Qian, Changsheng Xu. <em style="color: #d97706 !important;">Vision-Controllable Language Model for Image-guided Story Ending Generation.</em>
      </p>
      <div style="display: flex; flex-wrap: wrap; gap: 8px; margin-top: 8px;">
        <span style="padding: 4px 12px; background: rgba(245, 158, 11, 0.15); color: #fbbf24; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(245, 158, 11, 0.25);">Controllable Generation</span>
        <span style="padding: 4px 12px; background: rgba(245, 158, 11, 0.15); color: #fbbf24; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(245, 158, 11, 0.25);">Vision-Language</span>
        <span style="padding: 4px 12px; background: rgba(245, 158, 11, 0.15); color: #fbbf24; font-size: 11px; font-weight: 600; border-radius: 12px; border: 1px solid rgba(245, 158, 11, 0.25);">Cross-Modal Generation</span>
      </div>
    </div>
    <span style="padding: 8px 18px; background: linear-gradient(135deg, #f59e0b, #f97316); color: white; font-size: 12px; font-weight: 700; border-radius: 25px; white-space: nowrap; box-shadow: 0 4px 15px rgba(245, 158, 11, 0.3);">IEEE TMM (accepted)</span>
  </div>
</div>

</div>


<div style="text-align: center; margin: 50px 0 40px;">
  <h3 style="display: inline-flex; align-items: center; gap: 12px; margin: 0; padding: 10px 24px; background: linear-gradient(135deg, rgba(16, 185, 129, 0.1) 0%, rgba(5, 150, 105, 0.05) 100%); border: 2px solid rgba(16, 185, 129, 0.2); border-radius: 30px; font-size: 20px; color: #10b981; font-weight: 700;">
    📄 Co-author Papers
  </h3>
</div>

<div style="display: grid; gap: 14px; margin: 20px 0;">

<div style="position: relative; padding: 20px; background: rgba(30, 41, 59, 0.6); border: 2px solid rgba(71, 85, 105, 0.35); border-radius: 16px; transition: all 0.3s ease;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 14px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 15px; line-height: 1.7;">
        Shengsheng Qian, <strong style="color: #22d3ee; font-weight: 600;">Dizhan Xue</strong>, Quan Fang, Changsheng Xu. <em>Integrating Multi-Label Contrastive Learning with Dual Adversarial Graph Neural Networks for Cross-Modal Retrieval.</em>
      </p>
    </div>
    <span style="padding: 7px 16px; background: rgba(6, 182, 212, 0.25); color: #22d3ee; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.35);">IEEE TPAMI 2022</span>
  </div>
</div>

<div style="position: relative; padding: 20px; background: rgba(30, 41, 59, 0.6); border: 2px solid rgba(71, 85, 105, 0.35); border-radius: 16px; transition: all 0.3s ease;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 14px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 15px; line-height: 1.7;">
        Zhenyu Yang, <strong style="color: #22d3ee; font-weight: 600;">Dizhan Xue</strong>, Shengsheng Qian, Weiming Dong, Changsheng Xu. <em>LDRE: LLM-based Divergent Reasoning and Ensemble for Zero-Shot Composed Image Retrieval.</em>
      </p>
    </div>
    <span style="padding: 7px 16px; background: rgba(6, 182, 212, 0.25); color: #22d3ee; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.35);">ACM SIGIR 2024 ✨</span>
  </div>
</div>

<div style="position: relative; padding: 20px; background: rgba(30, 41, 59, 0.6); border: 2px solid rgba(71, 85, 105, 0.35); border-radius: 16px; transition: all 0.3s ease;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 14px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 15px; line-height: 1.7;">
        Yifei Wang, <strong style="color: #22d3ee; font-weight: 600;">Dizhan Xue</strong>, Shengjie Zhang, Shengsheng Qian. <em>BadAgent: Inserting and Activating Backdoor Attacks in LLM Agents.</em>
      </p>
    </div>
    <span style="padding: 7px 16px; background: rgba(6, 182, 212, 0.25); color: #22d3ee; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.35);">ACL 2024</span>
  </div>
</div>

<div style="position: relative; padding: 20px; background: rgba(30, 41, 59, 0.6); border: 2px solid rgba(71, 85, 105, 0.35); border-radius: 16px; transition: all 0.3s ease;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 14px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 15px; line-height: 1.7;">
        Shengsheng Qian, <strong style="color: #22d3ee; font-weight: 600;">Dizhan Xue</strong>, Quan Fang, Changsheng Xu. <em>Dual Adversarial Graph Neural Networks for Multi-Label Cross-Modal Retrieval.</em>
      </p>
    </div>
    <span style="padding: 7px 16px; background: rgba(6, 182, 212, 0.25); color: #22d3ee; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.35);">AAAI 2021</span>
  </div>
</div>

<div style="position: relative; padding: 20px; background: rgba(30, 41, 59, 0.6); border: 2px solid rgba(71, 85, 105, 0.35); border-radius: 16px; transition: all 0.3s ease;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 14px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 15px; line-height: 1.7;">
        Shengsheng Qian, <strong style="color: #22d3ee; font-weight: 600;">Dizhan Xue</strong>, Jun Hu, Huaiwen Zhang, Changsheng Xu. <em>Nonparametric Clustering-Guided Cross-View Contrastive Learning for Partially View-Aligned Representation Learning.</em>
      </p>
    </div>
    <span style="padding: 7px 16px; background: rgba(6, 182, 212, 0.25); color: #22d3ee; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.35);">IEEE TIP 2024</span>
  </div>
</div>

<div style="position: relative; padding: 20px; background: rgba(30, 41, 59, 0.6); border: 2px solid rgba(71, 85, 105, 0.35); border-radius: 16px; transition: all 0.3s ease;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 14px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 15px; line-height: 1.7;">
        Shengsheng Qian, <strong style="color: #22d3ee; font-weight: 600;">Dizhan Xue</strong>, Quan Fang, Changsheng Xu. <em>Adaptive Label-Aware Graph Convolutional Networks for Cross-Modal Retrieval.</em>
      </p>
    </div>
    <span style="padding: 7px 16px; background: rgba(6, 182, 212, 0.25); color: #22d3ee; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.35);">IEEE TMM 2021</span>
  </div>
</div>

<div style="position: relative; padding: 20px; background: rgba(30, 41, 59, 0.6); border: 2px solid rgba(71, 85, 105, 0.35); border-radius: 16px; transition: all 0.3s ease;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 14px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 15px; line-height: 1.7;">
        Shengsheng Qian, Hong Chen, <strong style="color: #22d3ee; font-weight: 600;">Dizhan Xue</strong>, Quan Fang, Changsheng Xu. <em>Open-World Social Event Classification.</em>
      </p>
    </div>
    <span style="padding: 7px 16px; background: rgba(6, 182, 212, 0.25); color: #22d3ee; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.35);">WWW 2023</span>
  </div>
</div>

<div style="position: relative; padding: 20px; background: rgba(30, 41, 59, 0.6); border: 2px solid rgba(71, 85, 105, 0.35); border-radius: 16px; transition: all 0.3s ease;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 14px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 15px; line-height: 1.7;">
        Zhenyu Yang, Shengsheng Qian, <strong style="color: #22d3ee; font-weight: 600;">Dizhan Xue</strong>, Jiahong Wu, Fan Yang, Weiming Dong, Changsheng Xu. <em>Semantic Editing Increment Benefits Zero-Shot Composed Image Retrieval.</em>
      </p>
    </div>
    <span style="padding: 7px 16px; background: rgba(6, 182, 212, 0.25); color: #22d3ee; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.35);">ACM MM 2024</span>
  </div>
</div>

<div style="position: relative; padding: 20px; background: rgba(30, 41, 59, 0.6); border: 2px solid rgba(71, 85, 105, 0.35); border-radius: 16px; transition: all 0.3s ease;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 14px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 15px; line-height: 1.7;">
        Shengsheng Qian, Shengjie Zhang, <strong style="color: #22d3ee; font-weight: 600;">Dizhan Xue</strong>, Huaiwen Zhang, Changsheng Xu. <em>Learning Temporal Event Knowledge for Continual Social Event Classification.</em>
      </p>
    </div>
    <span style="padding: 7px 16px; background: rgba(6, 182, 212, 0.25); color: #22d3ee; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.35);">IEEE TKDE 2025</span>
  </div>
</div>

<div style="position: relative; padding: 20px; background: rgba(30, 41, 59, 0.6); border: 2px solid rgba(71, 85, 105, 0.35); border-radius: 16px; transition: all 0.3s ease;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 14px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 15px; line-height: 1.7;">
        Zhenyu Yang, Yuhang Hu, Zemin Du, <strong style="color: #22d3ee; font-weight: 600;">Dizhan Xue</strong>, Shengsheng Qian, Jiahong Wu, Fan Yang, Weiming Dong, Changsheng Xu. <em>SVBench: A Benchmark with Temporal Multi-Turn Dialogues for Streaming Video Understanding.</em>
      </p>
    </div>
    <span style="padding: 7px 16px; background: rgba(6, 182, 212, 0.25); color: #22d3ee; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.35);">ICLR 2025</span>
  </div>
</div>

</div>


<div style="text-align: center; margin: 50px 0 40px;">
  <h3 style="display: inline-flex; align-items: center; gap: 12px; margin: 0; padding: 10px 24px; background: linear-gradient(135deg, rgba(245, 158, 11, 0.1) 0%, rgba(245, 158, 11, 0.05) 100%); border: 2px solid rgba(245, 158, 11, 0.2); border-radius: 30px; font-size: 20px; color: #f59e0b; font-weight: 700;">
    📌 Preprints
  </h3>
</div>

<div style="display: grid; gap: 16px; margin: 20px 0;">

<div style="position: relative; padding: 22px; background: rgba(30, 41, 59, 0.4); border: 2px dashed rgba(100, 116, 139, 0.5); border-radius: 16px; transition: all 0.3s ease;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 14px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0; color: #f1f5f9; font-size: 15px; line-height: 1.7; font-weight: 500;">
        <em>A Survey on Interpretable Cross-modal Reasoning.</em> CoRR abs/2309.01955 (2023).
      </p>
    </div>
    <span style="padding: 7px 16px; background: rgba(6, 182, 212, 0.25); color: #22d3ee; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap; border: 1px dashed rgba(6, 182, 212, 0.45);">arXiv 2023</span>
  </div>
</div>

<div style="position: relative; padding: 22px; background: rgba(30, 41, 59, 0.4); border: 2px dashed rgba(100, 116, 139, 0.5); border-radius: 16px; transition: all 0.3s ease;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 14px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 280px;">
      <p style="margin: 0; color: #f1f5f9; font-size: 15px; line-height: 1.7; font-weight: 500;">
        <em>Short-Video Propagation Influence Rating: A New Real-world Dataset and A New Large Graph Model.</em> CoRR abs/2503.23746 (2025).
      </p>
    </div>
    <span style="padding: 7px 16px; background: rgba(6, 182, 212, 0.25); color: #22d3ee; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap; border: 1px dashed rgba(6, 182, 212, 0.45);">arXiv 2025</span>
  </div>
</div>

</div>

<!-- Custom Divider -->
<div style="display: flex; align-items: center; justify-content: center; gap: 20px; margin: 80px 0; opacity: 0.6;">
  <div style="flex: 1; max-width: 200px; height: 1px; background: linear-gradient(90deg, transparent, #f59e0b, transparent);"></div>
  <div style="width: 10px; height: 10px; background: linear-gradient(135deg, #f59e0b, #f97316); border-radius: 50%; box-shadow: 0 0 10px rgba(245, 158, 11, 0.5);"></div>
  <div style="flex: 1; max-width: 200px; height: 1px; background: linear-gradient(90deg, transparent, #f59e0b, transparent);"></div>
</div>

<div style="text-align: center; margin: 80px 0 60px;">
  <div style="display: inline-flex; align-items: center; gap: 16px; padding: 12px 32px; background: linear-gradient(135deg, rgba(245, 158, 11, 0.1) 0%, rgba(245, 158, 11, 0.05) 100%); border: 2px solid rgba(245, 158, 11, 0.25); border-radius: 50px; backdrop-filter: blur(10px);">
    <span style="font-size: 32px; filter: drop-shadow(0 0 10px rgba(245, 158, 11, 0.5));">🏆</span>
    <h2 style="margin: 0; font-size: 28px; background: linear-gradient(135deg, #f59e0b, #f97316); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; font-weight: 800; letter-spacing: -1px; text-decoration: none !important; border: none !important; border-bottom: none !important; box-shadow: none !important; outline: none !important;">Selected Honors</h2>
  </div>
</div>

<div style="display: grid; gap: 20px; margin: 30px 0;">

<div style="padding: 25px; background: linear-gradient(135deg, rgba(251, 191, 36, 0.12) 0%, rgba(245, 158, 11, 0.06) 100%); border: 2px solid rgba(251, 191, 36, 0.35); border-radius: 16px; position: relative; overflow: hidden;">

  <!-- Decorative elements -->
  <div style="position: absolute; top: -20px; right: -20px; font-size: 120px; opacity: 0.05; transform: rotate(15deg);">🏆</div>

  <div style="position: relative; z-index: 1;">
    <div style="display: inline-flex; align-items: center; gap: 8px; padding: 8px 16px; background: linear-gradient(135deg, #f59e0b, #d97706); border-radius: 20px; margin-bottom: 16px;">
      <span style="font-size: 18px;">✨</span>
      <span style="color: white; font-size: 13px; font-weight: 700; letter-spacing: 1px;">Best Paper Honorable Mention</span>
    </div>

    <p style="margin: 0; color: #dd641eff; font-size: 15px; line-height: 1.7; font-weight: 500;">
      Zhenyu Yang, <strong style="color: #fc711aff; font-weight: 700;">Dizhan Xue</strong>, Shengsheng Qian, Weiming Dong, Changsheng Xu. <em>LDRE: LLM-based Divergent Reasoning and Ensemble for Zero-Shot Composed Image Retrieval.</em>
    </p>

    <div style="margin-top: 12px;">
      <span style="padding: 6px 14px; background: rgba(251, 191, 36, 0.25); color: #dd641eff; font-size: 11px; font-weight: 700; border-radius: 15px; border: 1px solid rgba(251, 191, 36, 0.4);">ACM SIGIR 2024</span>
    </div>
  </div>
</div>

<div style="padding: 25px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.12) 0%, rgba(14, 165, 233, 0.06) 100%); border: 2px solid rgba(6, 182, 212, 0.35); border-radius: 16px; position: relative; overflow: hidden;">

  <!-- Decorative elements -->
  <div style="position: absolute; top: -20px; right: -20px; font-size: 120px; opacity: 0.05; transform: rotate(15deg);">🌟</div>

  <div style="position: relative; z-index: 1;">
    <div style="display: inline-flex; align-items: center; gap: 8px; padding: 8px 16px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); border-radius: 20px; margin-bottom: 16px;">
      <span style="font-size: 18px;">🎖️</span>
      <span style="color: white; font-size: 13px; font-weight: 700; letter-spacing: 1px;">First-Class Academic Scholarship</span>
    </div>

    <p style="margin: 0; color: #198fd3ff; font-size: 15px; line-height: 1.7; font-weight: 500;">
      <strong style="color: #1cc8f8ff; font-weight: 700;">First-Class Academic Scholarship</strong> of University of Chinese Academy of Sciences (UCAS), awarded to top 5% students for outstanding academic performance.
    </p>

    <div style="margin-top: 12px;">
      <span style="padding: 6px 14px; background: rgba(6, 182, 212, 0.25); color: #198fd3ff; font-size: 11px; font-weight: 700; border-radius: 15px; border: 1px solid rgba(6, 182, 212, 0.4);">2018</span>
    </div>
  </div>
</div>

</div>

<!-- Custom Divider -->
<div style="display: flex; align-items: center; justify-content: center; gap: 20px; margin: 80px 0; opacity: 0.6;">
  <div style="flex: 1; max-width: 200px; height: 1px; background: linear-gradient(90deg, transparent, #10b981, transparent);"></div>
  <div style="width: 10px; height: 10px; background: linear-gradient(135deg, #10b981, #14b8a6); border-radius: 50%; box-shadow: 0 0 10px rgba(16, 185, 129, 0.5);"></div>
  <div style="flex: 1; max-width: 200px; height: 1px; background: linear-gradient(90deg, transparent, #10b981, transparent);"></div>
</div>

<div style="text-align: center; margin: 80px 0 60px;">
  <div style="display: inline-flex; align-items: center; gap: 16px; padding: 12px 32px; background: linear-gradient(135deg, rgba(16, 185, 129, 0.1) 0%, rgba(5, 150, 105, 0.05) 100%); border: 2px solid rgba(16, 185, 129, 0.2); border-radius: 50px; backdrop-filter: blur(10px);">
    <span style="font-size: 32px; filter: drop-shadow(0 0 10px rgba(16, 185, 129, 0.5));">💻</span>
    <h2 style="margin: 0; font-size: 28px; background: linear-gradient(135deg, #10b981, #14b8a6); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; font-weight: 800; letter-spacing: -1px; text-decoration: none !important; border: none !important; border-bottom: none !important; box-shadow: none !important; outline: none !important;">Projects</h2>
  </div>
</div>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 24px; margin: 30px 0;">

<div style="position: relative; padding: 28px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.12) 0%, rgba(14, 165, 233, 0.06) 100%); border: 2px solid rgba(6, 182, 212, 0.25); border-radius: 20px; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden;">
  <div style="position: absolute; top: 0; right: 0; width: 120px; height: 120px; background: radial-gradient(circle, rgba(6, 182, 212, 0.1) 0%, transparent 70%); filter: blur(30px);"></div>
  <div style="position: relative; z-index: 1; display: flex; align-items: center; gap: 14px; margin-bottom: 18px;">
    <div style="font-size: 42px; filter: drop-shadow(0 4px 8px rgba(6, 182, 212, 0.3));">📧</div>
    <div>
      <h4 style="margin: 0; color: #22d3ee; font-size: 20px; font-weight: 700;">MailMind</h4>
      <p style="margin: 4px 0 0; color: #cbd5e1; font-size: 13px; font-weight: 500;">Email Agent</p>
    </div>
  </div>
  <p style="position: relative; z-index: 1; margin: 0 0 16px; color: #cbd5e1; font-size: 15px; line-height: 1.6;">LLM-powered multi-step email assistant for intelligent email management.</p>
  <a href="https://github.com/LivXue/open-email-agent" style="position: relative; z-index: 1; display: inline-flex; align-items: center; gap: 8px; padding: 10px 20px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); color: white; text-decoration: none; font-size: 14px; font-weight: 600; border-radius: 12px; transition: all 0.3s ease; box-shadow: 0 4px 15px rgba(6, 182, 212, 0.3);">
    ⚡ View Project
  </a>
</div>

<div style="position: relative; padding: 28px; background: linear-gradient(135deg, rgba(16, 185, 129, 0.12) 0%, rgba(5, 150, 105, 0.06) 100%); border: 2px solid rgba(16, 185, 129, 0.25); border-radius: 20px; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden;">
  <div style="position: absolute; top: 0; right: 0; width: 120px; height: 120px; background: radial-gradient(circle, rgba(16, 185, 129, 0.1) 0%, transparent 70%); filter: blur(30px);"></div>
  <div style="position: relative; z-index: 1; display: flex; align-items: center; gap: 14px; margin-bottom: 18px;">
    <div style="font-size: 42px; filter: drop-shadow(0 4px 8px rgba(16, 185, 129, 0.3));">🔗</div>
    <div>
      <h4 style="margin: 0; color: #34d399; font-size: 20px; font-weight: 700;">GNN4CMR</h4>
      <p style="margin: 4px 0 0; color: #cbd5e1; font-size: 13px; font-weight: 500;">Cross-modal Retrieval</p>
    </div>
  </div>
  <p style="position: relative; z-index: 1; margin: 0 0 16px; color: #cbd5e1; font-size: 15px; line-height: 1.6;">Graph Neural Network and Toolkits for Cross-modal Retrieval tasks.</p>
  <a href="https://github.com/LivXue/GNN4CMR" style="position: relative; z-index: 1; display: inline-flex; align-items: center; gap: 8px; padding: 10px 20px; background: linear-gradient(135deg, #10b981, #14b8a6); color: white; text-decoration: none; font-size: 14px; font-weight: 600; border-radius: 12px; transition: all 0.3s ease; box-shadow: 0 4px 15px rgba(16, 185, 129, 0.3);">
    ⚡ View Project
  </a>
</div>

</div>

<!-- Custom Divider -->
<div style="display: flex; align-items: center; justify-content: center; gap: 20px; margin: 80px 0; opacity: 0.6;">
  <div style="flex: 1; max-width: 200px; height: 1px; background: linear-gradient(90deg, transparent, #06b6d4, transparent);"></div>
  <div style="width: 10px; height: 10px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); border-radius: 50%; box-shadow: 0 0 10px rgba(6, 182, 212, 0.5);"></div>
  <div style="flex: 1; max-width: 200px; height: 1px; background: linear-gradient(90deg, transparent, #06b6d4, transparent);"></div>
</div>

<div style="text-align: center; margin: 80px 0 60px;">
  <div style="display: inline-flex; align-items: center; gap: 16px; padding: 12px 32px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.1) 0%, rgba(14, 165, 233, 0.05) 100%); border: 2px solid rgba(6, 182, 212, 0.2); border-radius: 50px; backdrop-filter: blur(10px);">
    <span style="font-size: 32px; filter: drop-shadow(0 0 10px rgba(6, 182, 212, 0.5));">📫</span>
    <h2 style="margin: 0; font-size: 28px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; font-weight: 800; letter-spacing: -1px; text-decoration: none !important; border: none !important; border-bottom: none !important; box-shadow: none !important; outline: none !important;">Contact</h2>
  </div>
</div>

<div align="center">

<div style="display: flex; gap: 20px; justify-content: center; flex-wrap: wrap; margin: 40px 0;">

<div style="position: relative; padding: 28px 36px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.12) 0%, rgba(6, 182, 212, 0.06) 100%); border: 2px solid rgba(6, 182, 212, 0.3); border-radius: 20px; text-align: center; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden;">
  <div style="position: absolute; top: 0; right: 0; width: 100px; height: 100px; background: radial-gradient(circle, rgba(6, 182, 212, 0.15) 0%, transparent 70%); filter: blur(25px);"></div>
  <div style="position: relative; z-index: 1; font-size: 36px; margin-bottom: 12px; filter: drop-shadow(0 4px 8px rgba(6, 182, 212, 0.3));">📧</div>
  <p style="position: relative; z-index: 1; margin: 0; color: #0891b2; font-size: 15px; font-weight: 600;">xuedizhan17@mails.ucas.ac.cn</p>
</div>

<div style="position: relative; padding: 28px 36px; background: linear-gradient(135deg, rgba(14, 165, 233, 0.12) 0%, rgba(14, 165, 233, 0.06) 100%); border: 2px solid rgba(14, 165, 233, 0.3); border-radius: 20px; text-align: center; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden;">
  <div style="position: absolute; top: 0; right: 0; width: 100px; height: 100px; background: radial-gradient(circle, rgba(14, 165, 233, 0.15) 0%, transparent 70%); filter: blur(25px);"></div>
  <div style="position: relative; z-index: 1; font-size: 36px; margin-bottom: 12px; filter: drop-shadow(0 4px 8px rgba(14, 165, 233, 0.3));">🌐</div>
  <p style="position: relative; z-index: 1; margin: 0; color: #0284c7; font-size: 15px; font-weight: 600;">dblp.org/pid/293/9621</p>
</div>

<div style="position: relative; padding: 28px 36px; background: linear-gradient(135deg, rgba(16, 185, 129, 0.12) 0%, rgba(16, 185, 129, 0.06) 100%); border: 2px solid rgba(16, 185, 129, 0.3); border-radius: 20px; text-align: center; transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); overflow: hidden;">
  <div style="position: absolute; top: 0; right: 0; width: 100px; height: 100px; background: radial-gradient(circle, rgba(16, 185, 129, 0.15) 0%, transparent 70%); filter: blur(25px);"></div>
  <div style="position: relative; z-index: 1; font-size: 36px; margin-bottom: 12px; filter: drop-shadow(0 4px 8px rgba(16, 185, 129, 0.3));">🔗</div>
  <p style="position: relative; z-index: 1; margin: 0; color: #059669; font-size: 15px; font-weight: 600;">github.com/LivXue</p>
</div>

</div>

<div style="margin-top: 80px; padding: 40px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.08) 0%, rgba(14, 165, 233, 0.06) 100%); border: 2px solid rgba(6, 182, 212, 0.15); border-radius: 24px; position: relative; overflow: hidden;">
  <div style="position: absolute; top: 0; left: 0; width: 200px; height: 200px; background: radial-gradient(circle, rgba(6, 182, 212, 0.1) 0%, transparent 70%); filter: blur(40px);"></div>
  <div style="position: relative; z-index: 1;">
    <p style="margin: 0; color: #64748b; font-size: 14px; font-weight: 500;">
      💚 Built with passion for multimodal AI & intelligent systems
    </p>
    <p style="margin: 12px 0 0; color: #475569; font-size: 13px;">
      © 2025 Dizhan Xue · State Key Laboratory of Multimodal Artificial Intelligence Systems
    </p>
  </div>
</div>

</div>

<style>
  /* Global Background */
  body {
    background: linear-gradient(135deg, #0f172a 0%, #1e293b 50%, #0f172a 100%);
    background-attachment: fixed;
    min-height: 100vh;
  }

  /* Responsive Design */
  @media (max-width: 768px) {
    h1 { font-size: 36px !important; }
    .publication-card { flex-direction: column !important; }
  }

  /* Smooth Transitions */
  div { transition: all 0.3s ease; }

  /* Card Hover Effects */
  div[style*="border-radius: 20px"]:hover {
    transform: translateY(-4px);
    box-shadow: 0 20px 40px rgba(6, 182, 212, 0.2);
  }

  /* Project Link Hover */
  a[href*="github"] {
    transition: all 0.3s ease;
  }
  a[href*="github"]:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 25px rgba(6, 182, 212, 0.4);
  }

  /* Scrollbar Styling */
  ::-webkit-scrollbar { width: 10px; }
  ::-webkit-scrollbar-track { background: #0f172a; }
  ::-webkit-scrollbar-thumb {
    background: linear-gradient(135deg, #06b6d4, #0ea5e9);
    border-radius: 5px;
    border: 2px solid #0f172a;
  }
  ::-webkit-scrollbar-thumb:hover {
    background: linear-gradient(135deg, #22d3ee, #38bdf8);
  }

  /* Selection Styling */
  ::selection {
    background: rgba(6, 182, 212, 0.3);
    color: #22d3ee;
  }

  /* Link Styling */
  a {
    transition: all 0.3s ease;
  }

  /* Prevent underlines on headings */
  h1, h2, h3, h4, h5, h6 {
    text-decoration: none !important;
    border: none !important;
    border-bottom: none !important;
    box-shadow: none !important;
    outline: none !important;
  }

  /* Prevent underlines on heading links/anchors */
  h1 a, h2 a, h3 a, h4 a, h5 a, h6 a,
  h1:hover, h2:hover, h3:hover, h4:hover, h5:hover, h6:hover {
    text-decoration: none !important;
    border-bottom: none !important;
    box-shadow: none !important;
  }

  /* Remove any pseudo-element underlines */
  h1::before, h2::before, h3::before, h4::before, h5::before, h6::before,
  h1::after, h2::after, h3::after, h4::after, h5::after, h6::after {
    text-decoration: none !important;
    border: none !important;
  }
</style>
