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
  .hero-container {
    position: relative;
    padding: 80px 40px;
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
    background: radial-gradient(circle at 20% 80%, rgba(6, 182, 212, 0.12) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(14, 165, 233, 0.12) 0%, transparent 50%),
                radial-gradient(circle at 40% 40%, rgba(16, 185, 129, 0.08) 0%, transparent 50%);
    animation: gradientShift 15s ease infinite;
    pointer-events: none;
  }
  .hero-content {
    position: relative;
    z-index: 1;
  }
  .hero-badge {
    display: inline-block;
    padding: 8px 20px;
    background: linear-gradient(135deg, #06b6d4, #0ea5e9);
    border-radius: 50px;
    margin-bottom: 20px;
    animation: pulse 2s ease-in-out infinite;
  }
  .hero-title {
    font-size: 56px;
    font-weight: 800;
    background: linear-gradient(135deg, #fff 0%, #67e8f9 50%, #7dd3fc 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin: 20px 0;
    letter-spacing: -2px;
  }
  .hero-subtitle {
    font-size: 20px;
    color: #cbd5e1;
    margin: 0 0 30px;
    font-weight: 300;
    max-width: 600px;
    line-height: 1.6;
  }
  .social-link {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 12px 24px;
    background: rgba(6, 182, 212, 0.1);
    border: 1px solid rgba(6, 182, 212, 0.3);
    border-radius: 12px;
    color: #22d3ee;
    text-decoration: none;
    font-weight: 500;
    transition: all 0.3s ease;
    backdrop-filter: blur(10px);
  }
  .social-link:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 25px rgba(6, 182, 212, 0.3);
    border-color: rgba(6, 182, 212, 0.5);
  }
</style>

<div align="center">

<!-- Hero Section with Animated Gradient Background -->
<div class="hero-container">

  <!-- Animated Background Elements -->
  <div class="hero-bg"></div>

  <!-- Content -->
  <div class="hero-content">
    <div class="hero-badge">
      <span style="color: white; font-size: 13px; font-weight: 600; letter-spacing: 2px; text-transform: uppercase;">PhD Candidate</span>
    </div>

    <h1 class="hero-title">
      Dizhan Xue
    </h1>

    <p class="hero-subtitle">
      PhD Student @ <span style="color: #22d3ee; font-weight: 500;">State Key Laboratory of Multimodal Artificial Intelligence Systems, Institute of Automation, Chinese Academy of Sciences</span>
    </p>

    <!-- Social Links -->
    <div style="display: flex; gap: 12px; justify-content: center; flex-wrap: wrap;">
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

---

## 🎯 About Me

I'm a PhD candidate at the **State Key Laboratory of Multimodal Artificial Intelligence Systems**, Institute of Automation, Chinese Academy of Sciences (CASIA), advised by Prof. Changsheng Xu.

**My Research Vision**

My core research focuses on enabling AI to better understand and reason about complex multimodal information. I believe that **multimodal intelligence is the essential pathway to AGI**. Recently, I've been particularly interested in **LLM Agents** and their capabilities in sophisticated reasoning tasks.

**Research Philosophy**

> *"True intelligence lies not just in perception, but in reasoning across modalities to construct meaningful understanding."*

I'm passionate about building AI systems that can explain their reasoning process—because I believe interpretability is crucial for trustworthy AI.

---

## 🎓 Education

<div style="display: grid; gap: 20px; margin: 30px 0;">

<!-- PhD -->
<div style="position: relative; padding: 25px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.08) 0%, rgba(14, 165, 233, 0.08) 100%); border: 1px solid rgba(6, 182, 212, 0.2); border-radius: 16px; transition: all 0.3s ease;">
  <div style="position: absolute; top: 20px; right: 20px;">
    <span style="padding: 6px 14px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); color: white; font-size: 11px; font-weight: 700; letter-spacing: 1px; border-radius: 20px; text-transform: uppercase;">Current</span>
  </div>

  <div style="display: flex; align-items: flex-start; gap: 15px; margin-bottom: 12px;">
    <span style="font-size: 28px;">🔬</span>
    <div style="flex: 1;">
      <h3 style="margin: 0 0 8px; font-size: 18px; color: #1e293b;">PhD in Pattern Recognition and Intelligent Systems</h3>
      <p style="margin: 0; color: #0891b2; font-size: 14px;">Institute of Automation, Chinese Academy of Sciences (CASIA)</p>
    </div>
  </div>

  <div style="margin: 15px 0; padding: 12px 16px; background: rgba(15, 23, 42, 0.5); border-radius: 8px;">
    <p style="margin: 0; color: #94a3b8; font-size: 13px;">
      <span style="color: #06b6d4; font-weight: 600;">📅 Sep 2021 - Jun 2026</span><br>
      <span style="color: #e2e8f0; font-weight: 500;">👨‍🏫 Supervisor:</span> <span style="color: #cbd5e1;">Prof. Changsheng Xu</span><br>
      <span style="color: #e2e8f0; font-weight: 500;">📝 Thesis:</span> <span style="color: #cbd5e1;">Multimodal Reasoning in Complicated Scenarios</span>
    </p>
  </div>
</div>

<!-- Bachelor -->
<div style="position: relative; padding: 25px; background: linear-gradient(135deg, rgba(16, 185, 129, 0.06) 0%, rgba(5, 150, 105, 0.06) 100%); border: 1px solid rgba(16, 185, 129, 0.2); border-radius: 16px; transition: all 0.3s ease;">
  <div style="display: flex; align-items: flex-start; gap: 15px; margin-bottom: 12px;">
    <span style="font-size: 28px;">🎓</span>
    <div style="flex: 1;">
      <h3 style="margin: 0 0 8px; font-size: 18px; color: #1e293b;">Bachelor of Computer Science and Technology</h3>
      <p style="margin: 0; color: #059669; font-size: 14px;">University of Chinese Academy of Sciences (UCAS)</p>
    </div>
  </div>

  <div style="margin: 15px 0; padding: 12px 16px; background: rgba(15, 23, 42, 0.5); border-radius: 8px;">
    <p style="margin: 0; color: #94a3b8; font-size: 13px;">
      <span style="color: #10b981; font-weight: 600;">📅 Sep 2017 - Jun 2021</span><br>
      <span style="color: #e2e8f0; font-weight: 500;">👨‍🏫 Supervisor:</span> <span style="color: #cbd5e1;">Prof. Changsheng Xu</span><br>
      <span style="color: #e2e8f0; font-weight: 500;">📝 Thesis:</span> <span style="color: #cbd5e1;">Debiased Short Video Recommendation Based on Counterfactual Reasoning</span>
    </p>
  </div>
</div>

</div>

---

## 🧠 Research Interests

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 16px; margin: 30px 0;">

<div style="padding: 24px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.1) 0%, rgba(6, 182, 212, 0.05) 100%); border: 1px solid rgba(6, 182, 212, 0.2); border-radius: 16px; text-align: center; transition: all 0.3s ease;">
  <div style="font-size: 36px; margin-bottom: 12px;">🔗</div>
  <h4 style="margin: 0 0 8px; color: #0891b2; font-size: 16px;">Multimodal Reasoning</h4>
  <p style="margin: 0; color: #64748b; font-size: 13px;">& Explainable AI</p>
</div>

<div style="padding: 24px; background: linear-gradient(135deg, rgba(14, 165, 233, 0.1) 0%, rgba(14, 165, 233, 0.05) 100%); border: 1px solid rgba(14, 165, 233, 0.2); border-radius: 16px; text-align: center; transition: all 0.3s ease;">
  <div style="font-size: 36px; margin-bottom: 12px;">🤖</div>
  <h4 style="margin: 0 0 8px; color: #0284c7; font-size: 16px;">Multimodal LLMs</h4>
  <p style="margin: 0; color: #64748b; font-size: 13px;">Vision-Language Models</p>
</div>

<div style="padding: 24px; background: linear-gradient(135deg, rgba(16, 185, 129, 0.1) 0%, rgba(16, 185, 129, 0.05) 100%); border: 1px solid rgba(16, 185, 129, 0.2); border-radius: 16px; text-align: center; transition: all 0.3s ease;">
  <div style="font-size: 36px; margin-bottom: 12px;">🎯</div>
  <h4 style="margin: 0 0 8px; color: #059669; font-size: 16px;">LLM Agents</h4>
  <p style="margin: 0; color: #64748b; font-size: 13px;">& Autonomous Systems</p>
</div>

</div>

---

## 📚 Publications

### 📖 **First-author Papers**

<div style="display: grid; gap: 16px; margin: 20px 0;">

<div style="padding: 20px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.08) 0%, rgba(6, 182, 212, 0.03) 100%); border-left: 3px solid #06b6d4; border-radius: 0 12px 12px 0;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0 0 8px; color: #0f172a; font-size: 15px; line-height: 1.6;">
        <strong style="color: #0891b2;">Dizhan Xue</strong>, Shengsheng Qian, Changsheng Xu. <em>Integrating Neural-Symbolic Reasoning With Variational Causal Inference Network for Explanatory Visual Question Answering.</em>
      </p>
    </div>
    <span style="padding: 6px 14px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); color: white; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap;">IEEE TPAMI 2024</span>
  </div>
</div>

<div style="padding: 20px; background: linear-gradient(135deg, rgba(14, 165, 233, 0.08) 0%, rgba(14, 165, 233, 0.03) 100%); border-left: 3px solid #0ea5e9; border-radius: 0 12px 12px 0;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0 0 8px; color: #0f172a; font-size: 15px; line-height: 1.6;">
        <strong style="color: #0284c7;">Dizhan Xue</strong>, Jing Cui, Shengsheng Qian, Chuanrui Hu, Changsheng Xu. <em>SoMe: A Realistic Benchmark for LLM-based Social Media Agents.</em>
      </p>
    </div>
    <span style="padding: 6px 14px; background: linear-gradient(135deg, #0ea5e9, #06b6d4); color: white; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap;">AAAI 2026</span>
  </div>
</div>

<div style="padding: 20px; background: linear-gradient(135deg, rgba(16, 185, 129, 0.08) 0%, rgba(16, 185, 129, 0.03) 100%); border-left: 3px solid #10b981; border-radius: 0 12px 12px 0;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0 0 8px; color: #0f172a; font-size: 15px; line-height: 1.6;">
        <strong style="color: #059669;">Dizhan Xue</strong>, Shengsheng Qian, Changsheng Xu. <em>Variational Causal Inference Network for Explanatory Visual Question Answering.</em>
      </p>
    </div>
    <span style="padding: 6px 14px; background: linear-gradient(135deg, #10b981, #14b8a6); color: white; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap;">ICCV 2023</span>
  </div>
</div>

<div style="padding: 20px; background: linear-gradient(135deg, rgba(245, 158, 11, 0.08) 0%, rgba(245, 158, 11, 0.03) 100%); border-left: 3px solid #f59e0b; border-radius: 0 12px 12px 0;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0 0 8px; color: #0f172a; font-size: 15px; line-height: 1.6;">
        <strong style="color: #d97706;">Dizhan Xue</strong>, Shengsheng Qian, Changsheng Xu. <em>Few-Shot Multimodal Explanation for Visual Question Answering.</em>
      </p>
    </div>
    <span style="padding: 6px 14px; background: linear-gradient(135deg, #f59e0b, #f97316); color: white; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap;">ACM MM 2024</span>
  </div>
</div>

<div style="padding: 20px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.08) 0%, rgba(6, 182, 212, 0.03) 100%); border-left: 3px solid #06b6d4; border-radius: 0 12px 12px 0;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0 0 8px; color: #0f172a; font-size: 15px; line-height: 1.6;">
        <strong style="color: #0891b2;">Dizhan Xue</strong>, Shengsheng Qian, Quan Fang, Changsheng Xu. <em>MMT: Image-guided Story Ending Generation with Multimodal Memory Transformer.</em>
      </p>
    </div>
    <span style="padding: 6px 14px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); color: white; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap;">ACM MM 2022</span>
  </div>
</div>

<div style="padding: 20px; background: linear-gradient(135deg, rgba(14, 165, 233, 0.08) 0%, rgba(14, 165, 233, 0.03) 100%); border-left: 3px solid #0ea5e9; border-radius: 0 12px 12px 0;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0 0 8px; color: #0f172a; font-size: 15px; line-height: 1.6;">
        <strong style="color: #0284c7;">Dizhan Xue</strong>, Shengsheng Qian, Xueshan Deng, Changsheng Xu. <em>A Unified Framework for Backdoor Trigger Segmentation.</em>
      </p>
    </div>
    <span style="padding: 6px 14px; background: linear-gradient(135deg, #0ea5e9, #06b6d4); color: white; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap;">IEEE TIP (accepted)</span>
  </div>
</div>

<div style="padding: 20px; background: linear-gradient(135deg, rgba(16, 185, 129, 0.08) 0%, rgba(16, 185, 129, 0.03) 100%); border-left: 3px solid #10b981; border-radius: 0 12px 12px 0;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0 0 8px; color: #0f172a; font-size: 15px; line-height: 1.6;">
        <strong style="color: #059669;">Dizhan Xue</strong>, Shengsheng Qian, Quan Fang, Changsheng Xu. <em>LININ: Logic Integrated Neural Inference Network for Explanatory Visual Question Answering.</em>
      </p>
    </div>
    <span style="padding: 6px 14px; background: linear-gradient(135deg, #10b981, #14b8a6); color: white; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap;">IEEE TMM 2024</span>
  </div>
</div>

<div style="padding: 20px; background: linear-gradient(135deg, rgba(245, 158, 11, 0.08) 0%, rgba(245, 158, 11, 0.03) 100%); border-left: 3px solid #f59e0b; border-radius: 0 12px 12px 0;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0 0 8px; color: #0f172a; font-size: 15px; line-height: 1.6;">
        <strong style="color: #d97706;">Dizhan Xue</strong>, Shengsheng Qian, Changsheng Xu. <em>Vision-Controllable Language Model for Image-guided Story Ending Generation.</em>
      </p>
    </div>
    <span style="padding: 6px 14px; background: linear-gradient(135deg, #f59e0b, #f97316); color: white; font-size: 11px; font-weight: 700; border-radius: 20px; white-space: nowrap;">IEEE TMM (accepted)</span>
  </div>
</div>

</div>

---

### 📄 **Co-author Papers**

<div style="display: grid; gap: 16px; margin: 20px 0;">

<div style="padding: 20px; background: rgba(30, 41, 59, 0.5); border: 1px solid rgba(71, 85, 105, 0.3); border-radius: 12px;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 14px; line-height: 1.6;">
        Shengsheng Qian, <strong>Dizhan Xue</strong>, Quan Fang, Changsheng Xu. <em>Integrating Multi-Label Contrastive Learning with Dual Adversarial Graph Neural Networks for Cross-Modal Retrieval.</em>
      </p>
    </div>
    <span style="padding: 5px 12px; background: rgba(6, 182, 212, 0.2); color: #22d3ee; font-size: 10px; font-weight: 600; border-radius: 15px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.3);">IEEE TPAMI 2022</span>
  </div>
</div>

<div style="padding: 20px; background: rgba(30, 41, 59, 0.5); border: 1px solid rgba(71, 85, 105, 0.3); border-radius: 12px;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 14px; line-height: 1.6;">
        Zhenyu Yang, <strong>Dizhan Xue</strong>, Shengsheng Qian, Weiming Dong, Changsheng Xu. <em>LDRE: LLM-based Divergent Reasoning and Ensemble for Zero-Shot Composed Image Retrieval.</em>
      </p>
    </div>
    <span style="padding: 5px 12px; background: rgba(6, 182, 212, 0.2); color: #22d3ee; font-size: 10px; font-weight: 600; border-radius: 15px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.3);">ACM SIGIR 2024 ✨</span>
  </div>
</div>

<div style="padding: 20px; background: rgba(30, 41, 59, 0.5); border: 1px solid rgba(71, 85, 105, 0.3); border-radius: 12px;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 14px; line-height: 1.6;">
        Yifei Wang, <strong>Dizhan Xue</strong>, Shengjie Zhang, Shengsheng Qian. <em>BadAgent: Inserting and Activating Backdoor Attacks in LLM Agents.</em>
      </p>
    </div>
    <span style="padding: 5px 12px; background: rgba(6, 182, 212, 0.2); color: #22d3ee; font-size: 10px; font-weight: 600; border-radius: 15px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.3);">ACL 2024</span>
  </div>
</div>

<div style="padding: 20px; background: rgba(30, 41, 59, 0.5); border: 1px solid rgba(71, 85, 105, 0.3); border-radius: 12px;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 14px; line-height: 1.6;">
        Shengsheng Qian, <strong>Dizhan Xue</strong>, Quan Fang, Changsheng Xu. <em>Dual Adversarial Graph Neural Networks for Multi-Label Cross-Modal Retrieval.</em>
      </p>
    </div>
    <span style="padding: 5px 12px; background: rgba(6, 182, 212, 0.2); color: #22d3ee; font-size: 10px; font-weight: 600; border-radius: 15px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.3);">AAAI 2021</span>
  </div>
</div>

<div style="padding: 20px; background: rgba(30, 41, 59, 0.5); border: 1px solid rgba(71, 85, 105, 0.3); border-radius: 12px;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 14px; line-height: 1.6;">
        Shengsheng Qian, <strong>Dizhan Xue</strong>, Jun Hu, Huaiwen Zhang, Changsheng Xu. <em>Nonparametric Clustering-Guided Cross-View Contrastive Learning for Partially View-Aligned Representation Learning.</em>
      </p>
    </div>
    <span style="padding: 5px 12px; background: rgba(6, 182, 212, 0.2); color: #22d3ee; font-size: 10px; font-weight: 600; border-radius: 15px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.3);">IEEE TIP 2024</span>
  </div>
</div>

<div style="padding: 20px; background: rgba(30, 41, 59, 0.5); border: 1px solid rgba(71, 85, 105, 0.3); border-radius: 12px;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 14px; line-height: 1.6;">
        Shengsheng Qian, <strong>Dizhan Xue</strong>, Quan Fang, Changsheng Xu. <em>Adaptive Label-Aware Graph Convolutional Networks for Cross-Modal Retrieval.</em>
      </p>
    </div>
    <span style="padding: 5px 12px; background: rgba(6, 182, 212, 0.2); color: #22d3ee; font-size: 10px; font-weight: 600; border-radius: 15px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.3);">IEEE TMM 2021</span>
  </div>
</div>

<div style="padding: 20px; background: rgba(30, 41, 59, 0.5); border: 1px solid rgba(71, 85, 105, 0.3); border-radius: 12px;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 14px; line-height: 1.6;">
        Shengsheng Qian, Hong Chen, <strong>Dizhan Xue</strong>, Quan Fang, Changsheng Xu. <em>Open-World Social Event Classification.</em>
      </p>
    </div>
    <span style="padding: 5px 12px; background: rgba(6, 182, 212, 0.2); color: #22d3ee; font-size: 10px; font-weight: 600; border-radius: 15px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.3);">WWW 2023</span>
  </div>
</div>

<div style="padding: 20px; background: rgba(30, 41, 59, 0.5); border: 1px solid rgba(71, 85, 105, 0.3); border-radius: 12px;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 14px; line-height: 1.6;">
        Zhenyu Yang, Shengsheng Qian, <strong>Dizhan Xue</strong>, Jiahong Wu, Fan Yang, Weiming Dong, Changsheng Xu. <em>Semantic Editing Increment Benefits Zero-Shot Composed Image Retrieval.</em>
      </p>
    </div>
    <span style="padding: 5px 12px; background: rgba(6, 182, 212, 0.2); color: #22d3ee; font-size: 10px; font-weight: 600; border-radius: 15px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.3);">ACM MM 2024</span>
  </div>
</div>

<div style="padding: 20px; background: rgba(30, 41, 59, 0.5); border: 1px solid rgba(71, 85, 105, 0.3); border-radius: 12px;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 14px; line-height: 1.6;">
        Shengsheng Qian, Shengjie Zhang, <strong>Dizhan Xue</strong>, Huaiwen Zhang, Changsheng Xu. <em>Learning Temporal Event Knowledge for Continual Social Event Classification.</em>
      </p>
    </div>
    <span style="padding: 5px 12px; background: rgba(6, 182, 212, 0.2); color: #22d3ee; font-size: 10px; font-weight: 600; border-radius: 15px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.3);">IEEE TKDE 2025</span>
  </div>
</div>

<div style="padding: 20px; background: rgba(30, 41, 59, 0.5); border: 1px solid rgba(71, 85, 105, 0.3); border-radius: 12px;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0; color: #e2e8f0; font-size: 14px; line-height: 1.6;">
        Zhenyu Yang, Yuhang Hu, Zemin Du, <strong>Dizhan Xue</strong>, Shengsheng Qian, Jiahong Wu, Fan Yang, Weiming Dong, Changsheng Xu. <em>SVBench: A Benchmark with Temporal Multi-Turn Dialogues for Streaming Video Understanding.</em>
      </p>
    </div>
    <span style="padding: 5px 12px; background: rgba(6, 182, 212, 0.2); color: #22d3ee; font-size: 10px; font-weight: 600; border-radius: 15px; white-space: nowrap; border: 1px solid rgba(6, 182, 212, 0.3);">ICLR 2025</span>
  </div>
</div>

</div>

---

### 📌 **Preprints**

<div style="display: grid; gap: 16px; margin: 20px 0;">

<div style="padding: 20px; background: rgba(30, 41, 59, 0.3); border: 1px dashed rgba(100, 116, 139, 0.4); border-radius: 12px;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0; color: #f1f5f9; font-size: 14px; line-height: 1.6;">
        <em>A Survey on Interpretable Cross-modal Reasoning.</em> CoRR abs/2309.01955 (2023).
      </p>
    </div>
    <span style="padding: 5px 12px; background: rgba(6, 182, 212, 0.2); color: #22d3ee; font-size: 10px; font-weight: 600; border-radius: 15px; white-space: nowrap; border: 1px dashed rgba(6, 182, 212, 0.4);">arXiv 2023</span>
  </div>
</div>

<div style="padding: 20px; background: rgba(30, 41, 59, 0.3); border: 1px dashed rgba(100, 116, 139, 0.4); border-radius: 12px;">
  <div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; flex-wrap: wrap;">
    <div style="flex: 1; min-width: 250px;">
      <p style="margin: 0; color: #f1f5f9; font-size: 14px; line-height: 1.6;">
        <em>Short-Video Propagation Influence Rating: A New Real-world Dataset and A New Large Graph Model.</em> CoRR abs/2503.23746 (2025).
      </p>
    </div>
    <span style="padding: 5px 12px; background: rgba(6, 182, 212, 0.2); color: #22d3ee; font-size: 10px; font-weight: 600; border-radius: 15px; white-space: nowrap; border: 1px dashed rgba(6, 182, 212, 0.4);">arXiv 2025</span>
  </div>
</div>

</div>

---

## 🏆 Selected Honors

<div style="display: grid; gap: 20px; margin: 30px 0;">

<div style="padding: 25px; background: linear-gradient(135deg, rgba(251, 191, 36, 0.12) 0%, rgba(245, 158, 11, 0.06) 100%); border: 2px solid rgba(251, 191, 36, 0.35); border-radius: 16px; position: relative; overflow: hidden;">

  <!-- Decorative elements -->
  <div style="position: absolute; top: -20px; right: -20px; font-size: 120px; opacity: 0.05; transform: rotate(15deg);">🏆</div>

  <div style="position: relative; z-index: 1;">
    <div style="display: inline-flex; align-items: center; gap: 8px; padding: 8px 16px; background: linear-gradient(135deg, #f59e0b, #d97706); border-radius: 20px; margin-bottom: 16px;">
      <span style="font-size: 18px;">✨</span>
      <span style="color: white; font-size: 13px; font-weight: 700; letter-spacing: 1px;">Best Paper Honorable Mention</span>
    </div>

    <p style="margin: 0; color: #78350f; font-size: 15px; line-height: 1.7; font-weight: 500;">
      Zhenyu Yang, <strong style="color: #92400e; font-weight: 700;">Dizhan Xue</strong>, Shengsheng Qian, Weiming Dong, Changsheng Xu. <em>LDRE: LLM-based Divergent Reasoning and Ensemble for Zero-Shot Composed Image Retrieval.</em>
    </p>

    <div style="margin-top: 12px;">
      <span style="padding: 6px 14px; background: rgba(251, 191, 36, 0.25); color: #78350f; font-size: 11px; font-weight: 700; border-radius: 15px; border: 1px solid rgba(251, 191, 36, 0.4);">ACM SIGIR 2024</span>
    </div>
  </div>
</div>

<div style="padding: 25px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.12) 0%, rgba(14, 165, 233, 0.06) 100%); border: 2px solid rgba(6, 182, 212, 0.35); border-radius: 16px; position: relative; overflow: hidden;">

  <!-- Decorative elements -->
  <div style="position: absolute; top: -20px; right: -20px; font-size: 120px; opacity: 0.05; transform: rotate(15deg);">🎓</div>

  <div style="position: relative; z-index: 1;">
    <div style="display: inline-flex; align-items: center; gap: 8px; padding: 8px 16px; background: linear-gradient(135deg, #06b6d4, #0ea5e9); border-radius: 20px; margin-bottom: 16px;">
      <span style="font-size: 18px;">🎖️</span>
      <span style="color: white; font-size: 13px; font-weight: 700; letter-spacing: 1px;">First-Class Academic Scholarship</span>
    </div>

    <p style="margin: 0; color: #0c4a6e; font-size: 15px; line-height: 1.7; font-weight: 500;">
      <strong style="color: #0e7490; font-weight: 700;">First-Class Academic Scholarship</strong> of University of Chinese Academy of Sciences (UCAS), awarded to top students for outstanding academic performance.
    </p>

    <div style="margin-top: 12px;">
      <span style="padding: 6px 14px; background: rgba(6, 182, 212, 0.25); color: #0c4a6e; font-size: 11px; font-weight: 700; border-radius: 15px; border: 1px solid rgba(6, 182, 212, 0.4);">2018</span>
    </div>
  </div>
</div>

</div>

---

## 💻 Projects

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 20px; margin: 30px 0;">

<div style="padding: 24px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.1) 0%, rgba(14, 165, 233, 0.05) 100%); border: 1px solid rgba(6, 182, 212, 0.2); border-radius: 16px; transition: all 0.3s ease;">
  <div style="display: flex; align-items: center; gap: 12px; margin-bottom: 16px;">
    <div style="font-size: 36px;">📧</div>
    <div>
      <h4 style="margin: 0; color: #0891b2; font-size: 18px;">MailMind</h4>
      <p style="margin: 4px 0 0; color: #64748b; font-size: 12px;">Email Agent</p>
    </div>
  </div>
  <p style="margin: 0 0 12px; color: #64748b; font-size: 14px;">LLM-powered multi-step email assistant for intelligent email management.</p>
  <a href="https://github.com/LivXue/open-email-agent" style="display: inline-flex; align-items: center; gap: 6px; color: #06b6d4; text-decoration: none; font-size: 13px; font-weight: 500;">
    ⚡ github.com/LivXue/open-email-agent
  </a>
</div>

<div style="padding: 24px; background: linear-gradient(135deg, rgba(16, 185, 129, 0.1) 0%, rgba(5, 150, 105, 0.05) 100%); border: 1px solid rgba(16, 185, 129, 0.2); border-radius: 16px; transition: all 0.3s ease;">
  <div style="display: flex; align-items: center; gap: 12px; margin-bottom: 16px;">
    <div style="font-size: 36px;">🔗</div>
    <div>
      <h4 style="margin: 0; color: #059669; font-size: 18px;">GNN4CMR</h4>
      <p style="margin: 4px 0 0; color: #64748b; font-size: 12px;">Cross-modal Retrieval</p>
    </div>
  </div>
  <p style="margin: 0 0 12px; color: #64748b; font-size: 14px;">Graph Neural Network for Cross-modal Retrieval tasks.</p>
  <a href="https://github.com/LivXue/GNN4CMR" style="display: inline-flex; align-items: center; gap: 6px; color: #10b981; text-decoration: none; font-size: 13px; font-weight: 500;">
    ⚡ github.com/LivXue/GNN4CMR
  </a>
</div>

</div>

---

## 📫 Contact

<div align="center">

<div style="display: flex; gap: 16px; justify-content: center; flex-wrap: wrap; margin: 30px 0;">

<div style="padding: 20px 30px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.1) 0%, rgba(6, 182, 212, 0.05) 100%); border: 1px solid rgba(6, 182, 212, 0.3); border-radius: 16px; text-align: center;">
  <div style="font-size: 28px; margin-bottom: 8px;">📧</div>
  <p style="margin: 0; color: #0891b2; font-size: 14px; font-weight: 500;">xuedizhan17@mails.ucas.ac.cn</p>
</div>

<div style="padding: 20px 30px; background: linear-gradient(135deg, rgba(14, 165, 233, 0.1) 0%, rgba(14, 165, 233, 0.05) 100%); border: 1px solid rgba(14, 165, 233, 0.3); border-radius: 16px; text-align: center;">
  <div style="font-size: 28px; margin-bottom: 8px;">🌐</div>
  <p style="margin: 0; color: #0284c7; font-size: 14px; font-weight: 500;">dblp.org/pid/293/9621</p>
</div>

<div style="padding: 20px 30px; background: linear-gradient(135deg, rgba(16, 185, 129, 0.1) 0%, rgba(16, 185, 129, 0.05) 100%); border: 1px solid rgba(16, 185, 129, 0.3); border-radius: 16px; text-align: center;">
  <div style="font-size: 28px; margin-bottom: 8px;">🔗</div>
  <p style="margin: 0; color: #059669; font-size: 14px; font-weight: 500;">github.com/LivXue</p>
</div>

</div>

---

<div style="margin-top: 60px; padding: 30px; background: linear-gradient(135deg, rgba(6, 182, 212, 0.05) 0%, rgba(14, 165, 233, 0.05) 100%); border-radius: 16px;">

<p style="margin: 0; color: #64748b; font-size: 13px;">
  💚 Built with passion for multimodal AI & intelligent systems
</p>
<p style="margin: 8px 0 0; color: #475569; font-size: 12px;">
  © 2025 Dizhan Xue · State Key Laboratory of Multimodal Artificial Intelligence Systems
</p>

</div>

</div>

<style>
  /* Responsive Design */
  @media (max-width: 768px) {
    h1 { font-size: 36px !important; }
    .publication-card { flex-direction: column !important; }
  }

  /* Smooth Transitions */
  div { transition: all 0.3s ease; }

  /* Scrollbar Styling */
  ::-webkit-scrollbar { width: 8px; }
  ::-webkit-scrollbar-track { background: #0f172a; }
  ::-webkit-scrollbar-thumb { background: linear-gradient(135deg, #06b6d4, #0ea5e9); border-radius: 4px; }
</style>
