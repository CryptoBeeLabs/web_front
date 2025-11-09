<template>
  <div class="min-h-screen">
  <!-- Navigation -->
      <nav class="fixed top-0 left-0 w-full z-50 bg-opacity-90 backdrop-blur-md bg-primary">
          <div class="container mx-auto px-4 py-4 flex justify-between items-center">
              <div class="flex items-center gap-2">
                  <img :src="logoPrimary" alt="CryptoBee Labs Logo" class="h-10 w-auto">
                  <div>
                      <span class="text-xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-white to-accent-light">CryptoBee Labs</span>
                      <p class="text-xs text-gray-400">Bee the win</p>
                  </div>
              </div>
  
              <!-- Desktop Navigation -->
              <div class="hidden md:flex items-center gap-8">
                  <a href="#home" class="nav-link text-white hover:text-accent-light transition-colors" data-lang-key="home">首页</a>
                  <a href="#products" class="nav-link text-white hover:text-accent-light transition-colors" data-lang-key="products">产品</a>
                  <a href="#strategies" class="nav-link text-white hover:text-accent-light transition-colors" data-lang-key="strategies">策略</a>
                  <a href="#ai-system" class="nav-link text-white hover:text-accent-light transition-colors" data-lang-key="ai-system">AI系统</a>
                  <a href="#dashboard" class="nav-link text-white hover:text-accent-light transition-colors" data-lang-key="dashboard">仪表盘</a>
                  <a href="#about" class="nav-link text-white hover:text-accent-light transition-colors" data-lang-key="about">关于我们</a>
                  <div class="relative group">
                      <button class="flex items-center gap-2 text-white hover:text-accent-light transition-colors">
                          <i class="fas fa-globe"></i>
                          <span id="current-language">中文简体</span>
                          <i class="fas fa-chevron-down text-xs"></i>
                      </button>
                      <div class="absolute right-0 mt-2 w-40 bg-primary border border-gray-700 rounded-lg shadow-lg opacity-0 invisible group-hover:opacity-100 group-hover:visible transition-all duration-300 z-50">
                          <ul>
                              <li><button class="w-full text-left px-4 py-2 hover:bg-primary-light transition-colors" data-lang="zh-CN">中文简体</button></li>
                              <li><button class="w-full text-left px-4 py-2 hover:bg-primary-light transition-colors" data-lang="zh-TW">中文繁体</button></li>
                              <li><button class="w-full text-left px-4 py-2 hover:bg-primary-light transition-colors" data-lang="en">English</button></li>
                          </ul>
                      </div>
                  </div>
                  <div class="flex gap-3">
                      <button class="btn-secondary px-4 py-2 rounded-lg text-white font-medium" data-lang-key="login">登录</button>
                      <button class="btn-primary px-4 py-2 rounded-lg text-white font-medium" data-lang-key="register">注册</button>
                  </div>
              </div>
  
              <!-- Mobile Menu Button -->
              <div class="md:hidden">
                  <button id="mobile-menu-button" class="text-white focus:outline-none">
                      <i class="fas fa-bars text-2xl"></i>
                  </button>
              </div>
          </div>
  
          <!-- Mobile Navigation -->
          <div id="mobile-menu" class="mobile-menu fixed top-0 left-0 h-full w-4/5 bg-primary z-50 p-6">
              <div class="flex justify-between items-center mb-8">
                  <div class="flex items-center gap-2">
                      <img :src="logoCompact" alt="CryptoBee Labs Logo" class="h-8 w-auto">
                      <span class="text-lg font-bold bg-clip-text text-transparent bg-gradient-to-r from-white to-accent-light">CryptoBee Labs</span>
                  </div>
                  <button id="close-menu-button" class="text-white focus:outline-none">
                      <i class="fas fa-times text-2xl"></i>
                  </button>
              </div>
              <div class="flex flex-col gap-6">
                  <a href="#home" class="text-white hover:text-accent-light transition-colors py-2 border-b border-gray-700" data-lang-key="home">首页</a>
                  <a href="#products" class="text-white hover:text-accent-light transition-colors py-2 border-b border-gray-700" data-lang-key="products">产品</a>
                  <a href="#strategies" class="text-white hover:text-accent-light transition-colors py-2 border-b border-gray-700" data-lang-key="strategies">策略</a>
                  <a href="#ai-system" class="text-white hover:text-accent-light transition-colors py-2 border-b border-gray-700" data-lang-key="ai-system">AI系统</a>
                  <a href="#dashboard" class="text-white hover:text-accent-light transition-colors py-2 border-b border-gray-700" data-lang-key="dashboard">仪表盘</a>
                  <a href="#about" class="text-white hover:text-accent-light transition-colors py-2 border-b border-gray-700" data-lang-key="about">关于我们</a>
                  <div class="py-2 border-b border-gray-700">
                      <div class="flex items-center justify-between">
                          <span class="text-white" data-lang-key="language">语言</span>
                          <div class="flex gap-2">
                              <button class="px-3 py-1 rounded bg-primary-light text-white" data-lang="zh-CN">中</button>
                              <button class="px-3 py-1 rounded bg-primary text-white hover:bg-primary-light" data-lang="zh-TW">繁</button>
                              <button class="px-3 py-1 rounded bg-primary text-white hover:bg-primary-light" data-lang="en">EN</button>
                          </div>
                      </div>
                  </div>
                  <div class="flex flex-col gap-3 mt-4">
                      <button class="btn-secondary px-4 py-3 rounded-lg text-white font-medium" data-lang-key="login">登录</button>
                      <button class="btn-primary px-4 py-3 rounded-lg text-white font-medium" data-lang-key="register">注册</button>
                  </div>
              </div>
          </div>
      </nav>
  
      <!-- Hero Section -->
      <section id="home" class="relative min-h-screen flex items-center justify-center overflow-hidden">
          <canvas id="hero-canvas"></canvas>
          <div class="container mx-auto px-4 py-20 relative z-10">
              <div class="flex flex-col md:flex-row items-center">
                  <div class="md:w-1/2 hero-content">
                      <h1 class="text-4xl md:text-6xl font-bold mb-6 leading-tight">
                          <span class="gradient-text" data-lang-key="hero-title">智能量化交易</span><br>
                          <span data-lang-key="hero-subtitle">加密资产的未来</span>
                      </h1>
                      <p class="text-lg md:text-xl text-gray-300 mb-8 max-w-lg" data-lang-key="hero-description">
                          CryptoBee Labs 提供专业的加密货币量化交易工具和策略，帮助投资者在数字资产市场中获取稳定收益。
                      </p>
                      <div class="flex flex-col sm:flex-row gap-4">
                          <button class="btn-primary px-8 py-4 rounded-lg text-white font-medium text-lg flex items-center justify-center gap-2">
                              <i class="fas fa-rocket"></i>
                              <span data-lang-key="hero-cta-1">开始使用</span>
                          </button>
                          <button class="btn-secondary px-8 py-4 rounded-lg text-white font-medium text-lg flex items-center justify-center gap-2">
                              <i class="fas fa-play-circle"></i>
                              <span data-lang-key="hero-cta-2">观看演示</span>
                          </button>
                      </div>
                      <div class="mt-12 flex items-center gap-6">
                          <div class="flex -space-x-2">
                              <img :src="userMen32" alt="User" class="w-10 h-10 rounded-full border-2 border-primary">
                              <img :src="userWomen44" alt="User" class="w-10 h-10 rounded-full border-2 border-primary">
                              <img :src="userMen86" alt="User" class="w-10 h-10 rounded-full border-2 border-primary">
                          </div>
                          <div>
                              <div class="flex items-center gap-1 text-warning">
                                  <i class="fas fa-star"></i>
                                  <i class="fas fa-star"></i>
                                  <i class="fas fa-star"></i>
                                  <i class="fas fa-star"></i>
                                  <i class="fas fa-star-half-alt"></i>
                                  <span class="ml-2 text-white">4.8/5</span>
                              </div>
                              <p class="text-sm text-gray-400">来自 1000+ 满意用户</p>
                          </div>
                      </div>
                  </div>
                  <div class="md:w-1/2 mt-12 md:mt-0 flex justify-center">
                      <img :src="heroDashboard" alt="Trading Dashboard" class="w-full max-w-lg rounded-xl shadow-2xl animate-float">
                  </div>
              </div>
          </div>
          <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce">
              <a href="#products" class="text-white opacity-70 hover:opacity-100 transition-opacity">
                  <i class="fas fa-chevron-down text-2xl"></i>
              </a>
          </div>
      </section>
  
      <!-- Products Section -->
      <section id="products" class="py-20 bg-gradient-to-b from-primary to-primary-light">
          <div class="container mx-auto px-4">
              <div class="text-center mb-16">
                  <h2 class="text-3xl md:text-5xl font-bold mb-4" data-lang-key="products-title">我们的产品</h2>
                  <p class="text-xl text-gray-300 max-w-2xl mx-auto" data-lang-key="products-description">
                      为加密货币投资者提供全方位的量化交易工具和解决方案
                  </p>
              </div>
  
              <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                  <!-- Product Card 1 -->
                  <div class="card p-8 feature-card">
                      <div class="feature-icon">
                          <i class="fas fa-chart-line text-2xl text-white"></i>
                      </div>
                      <h3 class="text-2xl font-bold mb-4">QuantStrategy Pro</h3>
                      <p class="text-gray-300 mb-6">
                          专业级量化交易策略平台，支持多种加密货币，提供回测、优化和实时交易功能。
                      </p>
                      <ul class="space-y-3 mb-8">
                          <li class="flex items-center gap-2">
                              <i class="fas fa-check text-success"></i>
                              <span>100+ 内置策略模板</span>
                          </li>
                          <li class="flex items-center gap-2">
                              <i class="fas fa-check text-success"></i>
                              <span>高性能回测引擎</span>
                          </li>
                          <li class="flex items-center gap-2">
                              <i class="fas fa-check text-success"></i>
                              <span>多交易所API集成</span>
                          </li>
                      </ul>
                      <button class="btn-primary w-full py-3 rounded-lg text-white font-medium">
                          了解更多
                      </button>
                  </div>
  
                  <!-- Product Card 2 -->
                  <div class="card p-8 feature-card">
                      <div class="feature-icon">
                          <i class="fas fa-robot text-2xl text-white"></i>
                      </div>
                      <h3 class="text-2xl font-bold mb-4">AI Advisor</h3>
                      <p class="text-gray-300 mb-6">
                          基于人工智能的投资顾问，根据市场状况和用户风险偏好，提供个性化投资建议。
                      </p>
                      <ul class="space-y-3 mb-8">
                          <li class="flex items-center gap-2">
                              <i class="fas fa-check text-success"></i>
                              <span>机器学习预测模型</span>
                          </li>
                          <li class="flex items-center gap-2">
                              <i class="fas fa-check text-success"></i>
                              <span>风险评估与管理</span>
                          </li>
                          <li class="flex items-center gap-2">
                              <i class="fas fa-check text-success"></i>
                              <span>智能投资组合优化</span>
                          </li>
                      </ul>
                      <button class="btn-primary w-full py-3 rounded-lg text-white font-medium">
                          了解更多
                      </button>
                  </div>
  
                  <!-- Product Card 3 -->
                  <div class="card p-8 feature-card">
                      <div class="feature-icon">
                          <i class="fas fa-server text-2xl text-white"></i>
                      </div>
                      <h3 class="text-2xl font-bold mb-4">DataHub</h3>
                      <p class="text-gray-300 mb-6">
                          全面的加密货币市场数据中心，提供高质量的历史和实时市场数据，支持策略研究。
                      </p>
                      <ul class="space-y-3 mb-8">
                          <li class="flex items-center gap-2">
                              <i class="fas fa-check text-success"></i>
                              <span>多维度市场数据</span>
                          </li>
                          <li class="flex items-center gap-2">
                              <i class="fas fa-check text-success"></i>
                              <span>高性能数据API</span>
                          </li>
                          <li class="flex items-center gap-2">
                              <i class="fas fa-check text-success"></i>
                              <span>自定义数据导出</span>
                          </li>
                      </ul>
                      <button class="btn-primary w-full py-3 rounded-lg text-white font-medium">
                          了解更多
                      </button>
                  </div>
              </div>
  
              <div class="mt-16 text-center">
                  <button class="btn-secondary px-8 py-3 rounded-lg text-white font-medium inline-flex items-center gap-2">
                      <i class="fas fa-th-large"></i>
                      查看全部产品
                  </button>
              </div>
          </div>
      </section>
  
      <!-- Strategies Section -->
      <section id="strategies" class="py-20 bg-primary-light">
          <div class="container mx-auto px-4">
              <div class="text-center mb-16">
                  <h2 class="text-3xl md:text-5xl font-bold mb-4" data-lang-key="strategies-title">量化策略</h2>
                  <p class="text-xl text-gray-300 max-w-2xl mx-auto" data-lang-key="strategies-description">
                      基于先进的数学模型和算法，我们的策略帮助投资者在不同市场环境中获取稳定收益
                  </p>
              </div>
  
              <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-12">
                  <!-- Strategy Selection -->
                  <div class="card p-6">
                      <h3 class="text-2xl font-bold mb-6">选择策略</h3>
                      <div class="space-y-4">
                          <div class="strategy-card card p-4 active" data-strategy="mean-reversion">
                              <div class="flex justify-between items-center">
                                  <div>
                                      <h4 class="text-xl font-semibold">均值回归策略</h4>
                                      <p class="text-sm text-gray-400">适合震荡市场</p>
                                  </div>
                                  <div class="flex items-center gap-2">
                                      <span class="text-success font-medium">+12.5%</span>
                                      <span class="text-sm text-gray-400">年化收益</span>
                                  </div>
                              </div>
                          </div>
  
                          <div class="strategy-card card p-4" data-strategy="momentum">
                              <div class="flex justify-between items-center">
                                  <div>
                                      <h4 class="text-xl font-semibold">动量策略</h4>
                                      <p class="text-sm text-gray-400">适合趋势市场</p>
                                  </div>
                                  <div class="flex items-center gap-2">
                                      <span class="text-success font-medium">+18.7%</span>
                                      <span class="text-sm text-gray-400">年化收益</span>
                                  </div>
                              </div>
                          </div>
  
                          <div class="strategy-card card p-4" data-strategy="arbitrage">
                              <div class="flex justify-between items-center">
                                  <div>
                                      <h4 class="text-xl font-semibold">套利策略</h4>
                                      <p class="text-sm text-gray-400">低风险稳定收益</p>
                                  </div>
                                  <div class="flex items-center gap-2">
                                      <span class="text-success font-medium">+8.3%</span>
                                      <span class="text-sm text-gray-400">年化收益</span>
                                  </div>
                              </div>
                          </div>
  
                          <div class="strategy-card card p-4" data-strategy="ml-based">
                              <div class="flex justify-between items-center">
                                  <div>
                                      <h4 class="text-xl font-semibold">机器学习策略</h4>
                                      <p class="text-sm text-gray-400">AI驱动的预测模型</p>
                                  </div>
                                  <div class="flex items-center gap-2">
                                      <span class="text-success font-medium">+22.1%</span>
                                      <span class="text-sm text-gray-400">年化收益</span>
                                  </div>
                              </div>
                          </div>
  
                          <div class="strategy-card card p-4" data-strategy="multi-factor">
                              <div class="flex justify-between items-center">
                                  <div>
                                      <h4 class="text-xl font-semibold">多因子策略</h4>
                                      <p class="text-sm text-gray-400">综合多种市场因素</p>
                                  </div>
                                  <div class="flex items-center gap-2">
                                      <span class="text-success font-medium">+15.6%</span>
                                      <span class="text-sm text-gray-400">年化收益</span>
                                  </div>
                              </div>
                          </div>
                      </div>
                  </div>
  
                  <!-- Strategy Backtest -->
                  <div class="card p-6">
                      <div class="flex justify-between items-center mb-6">
                          <h3 class="text-2xl font-bold">策略回测</h3>
                          <div class="ai-badge">
                              <i class="fas fa-brain"></i>
                              AI优化
                          </div>
                      </div>
  
                      <div class="mb-6">
                          <div class="flex justify-between items-center mb-2">
                              <span class="text-gray-300">回测周期</span>
                              <select class="bg-primary border border-gray-700 rounded px-3 py-1 text-white">
                                  <option>过去1年</option>
                                  <option>过去6个月</option>
                                  <option>过去3个月</option>
                                  <option>自定义</option>
                              </select>
                          </div>
                          <div class="flex justify-between items-center mb-2">
                              <span class="text-gray-300">初始资金</span>
                              <input type="text" value="10,000 USDT" class="bg-primary border border-gray-700 rounded px-3 py-1 text-white w-32">
                          </div>
                          <div class="flex justify-between items-center">
                              <span class="text-gray-300">交易费用</span>
                              <input type="text" value="0.1%" class="bg-primary border border-gray-700 rounded px-3 py-1 text-white w-32">
                          </div>
                      </div>
  
                      <div class="chart-container mb-6">
                          <canvas id="backtest-chart"></canvas>
                      </div>
  
                      <div class="grid grid-cols-2 gap-4 mb-6">
                          <div class="bg-primary p-4 rounded-lg">
                              <p class="text-gray-400 text-sm">年化收益率</p>
                              <p class="text-2xl font-bold text-success">+12.5%</p>
                          </div>
                          <div class="bg-primary p-4 rounded-lg">
                              <p class="text-gray-400 text-sm">最大回撤</p>
                              <p class="text-2xl font-bold text-danger">-8.3%</p>
                          </div>
                          <div class="bg-primary p-4 rounded-lg">
                              <p class="text-gray-400 text-sm">夏普比率</p>
                              <p class="text-2xl font-bold">1.85</p>
                          </div>
                          <div class="bg-primary p-4 rounded-lg">
                              <p class="text-gray-400 text-sm">胜率</p>
                              <p class="text-2xl font-bold">62.7%</p>
                          </div>
                      </div>
  
                      <div class="flex gap-4">
                          <button class="btn-primary flex-1 py-3 rounded-lg text-white font-medium">
                              运行回测
                          </button>
                          <button class="btn-secondary flex-1 py-3 rounded-lg text-white font-medium">
                              导出报告
                          </button>
                      </div>
                  </div>
              </div>
  
              <div class="card p-8">
                  <h3 class="text-2xl font-bold mb-6">策略详情</h3>
                  <div id="strategy-details">
                      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                          <div>
                              <h4 class="text-xl font-semibold mb-4">均值回归策略</h4>
                              <p class="text-gray-300 mb-6">
                                  均值回归策略基于市场价格会围绕其平均值波动的假设，当价格偏离均值较远时，预期会向均值回归。该策略适合震荡市场环境，在价格大幅波动时捕捉反转机会。
                              </p>
                              <h5 class="text-lg font-semibold mb-3">核心参数</h5>
                              <ul class="space-y-2 mb-6">
                                  <li class="flex justify-between">
                                      <span class="text-gray-400">均值周期</span>
                                      <span>20天</span>
                                  </li>
                                  <li class="flex justify-between">
                                      <span class="text-gray-400">标准差倍数</span>
                                      <span>2.0</span>
                                  </li>
                                  <li class="flex justify-between">
                                      <span class="text-gray-400">持仓周期</span>
                                      <span>3-5天</span>
                                  </li>
                                  <li class="flex justify-between">
                                      <span class="text-gray-400">止损比例</span>
                                      <span>5%</span>
                                  </li>
                              </ul>
                          </div>
                          <div>
                              <h5 class="text-lg font-semibold mb-3">适用市场条件</h5>
                              <div class="space-y-4 mb-6">
                                  <div class="flex items-center gap-3">
                                      <div class="w-3 h-3 rounded-full bg-success"></div>
                                      <span>市场波动性适中</span>
                                  </div>
                                  <div class="flex items-center gap-3">
                                      <div class="w-3 h-3 rounded-full bg-success"></div>
                                      <span>无明显趋势方向</span>
                                  </div>
                                  <div class="flex items-center gap-3">
                                      <div class="w-3 h-3 rounded-full bg-danger"></div>
                                      <span>强烈单边趋势市场</span>
                                  </div>
                                  <div class="flex items-center gap-3">
                                      <div class="w-3 h-3 rounded-full bg-danger"></div>
                                      <span>极端市场情绪期间</span>
                                  </div>
                              </div>
                              <button class="btn-primary w-full py-3 rounded-lg text-white font-medium">
                                  应用此策略
                              </button>
                          </div>
                      </div>
                  </div>
              </div>
          </div>
      </section>
  
      <!-- AI System Section -->
      <section id="ai-system" class="py-20 bg-gradient-to-b from-primary-light to-secondary">
          <div class="container mx-auto px-4">
              <div class="text-center mb-16">
                  <div class="ai-badge mb-4 mx-auto">
                      <i class="fas fa-brain"></i>
                      <span data-lang-key="ai-driven">AI驱动</span>
                  </div>
                  <h2 class="text-3xl md:text-5xl font-bold mb-4" data-lang-key="ai-system-title">智能策略推荐系统</h2>
                  <p class="text-xl text-gray-300 max-w-2xl mx-auto" data-lang-key="ai-system-description">
                      基于人工智能的策略推荐系统，根据市场状况和用户风险偏好，实时生成个性化投资建议
                  </p>
              </div>
  
              <div class="flex flex-col lg:flex-row gap-8">
                  <div class="lg:w-1/2">
                      <div class="card p-8 h-full">
                          <h3 class="text-2xl font-bold mb-6">风险偏好设置</h3>
                          <div class="space-y-6">
                              <div>
                                  <label class="block text-gray-300 mb-2">风险承受能力</label>
                                  <div class="flex items-center gap-4">
                                      <span class="text-sm text-gray-400">低</span>
                                      <input type="range" min="1" max="5" value="3" class="w-full h-2 bg-gray-700 rounded-lg appearance-none cursor-pointer">
                                      <span class="text-sm text-gray-400">高</span>
                                  </div>
                                  <div class="flex justify-between mt-1">
                                      <span class="text-xs text-gray-500">保守型</span>
                                      <span class="text-xs text-gray-500">平衡型</span>
                                      <span class="text-xs text-gray-500">激进型</span>
                                  </div>
                              </div>
  
                              <div>
                                  <label class="block text-gray-300 mb-2">投资期限</label>
                                  <div class="grid grid-cols-3 gap-4">
                                      <button class="bg-primary border border-gray-700 rounded-lg py-2 px-4 text-center hover:border-accent transition-colors">短期 (1-3月)</button>
                                      <button class="bg-primary border border-accent rounded-lg py-2 px-4 text-center">中期 (3-12月)</button>
                                      <button class="bg-primary border border-gray-700 rounded-lg py-2 px-4 text-center hover:border-accent transition-colors">长期 (1年+)</button>
                                  </div>
                              </div>
  
                              <div>
                                  <label class="block text-gray-300 mb-2">感兴趣的加密货币</label>
                                  <div class="flex flex-wrap gap-3">
                                      <div class="bg-primary border border-accent rounded-full py-1 px-4 flex items-center gap-2">
                                          <span class="w-2 h-2 rounded-full bg-orange-500"></span>
                                          <span>BTC</span>
                                          <button class="text-xs text-gray-400 hover:text-white">×</button>
                                      </div>
                                      <div class="bg-primary border border-accent rounded-full py-1 px-4 flex items-center gap-2">
                                          <span class="w-2 h-2 rounded-full bg-blue-500"></span>
                                          <span>ETH</span>
                                          <button class="text-xs text-gray-400 hover:text-white">×</button>
                                      </div>
                                      <div class="bg-primary border border-gray-700 rounded-full py-1 px-4 flex items-center gap-2 hover:border-accent transition-colors">
                                          <span class="w-2 h-2 rounded-full bg-purple-500"></span>
                                          <span>SOL</span>
                                          <button class="text-xs text-gray-400 hover:text-white">×</button>
                                      </div>
                                      <div class="bg-primary border border-gray-700 rounded-full py-1 px-4 flex items-center gap-2 hover:border-accent transition-colors">
                                          <span class="w-2 h-2 rounded-full bg-green-500"></span>
                                          <span>ADA</span>
                                          <button class="text-xs text-gray-400 hover:text-white">×</button>
                                      </div>
                                      <div class="bg-primary border border-dashed border-gray-500 rounded-full py-1 px-4 flex items-center gap-2 hover:border-accent transition-colors">
                                          <i class="fas fa-plus text-xs"></i>
                                          <span>添加</span>
                                      </div>
                                  </div>
                              </div>
  
                              <div>
                                  <label class="block text-gray-300 mb-2">投资目标</label>
                                  <textarea class="w-full bg-primary border border-gray-700 rounded-lg p-3 h-24 text-white" placeholder="例如：稳定增长，跑赢比特币，对冲通胀风险..."></textarea>
                              </div>
  
                              <button class="btn-primary w-full py-3 rounded-lg text-white font-medium">
                                  生成投资建议
                              </button>
                          </div>
                      </div>
                  </div>
  
                  <div class="lg:w-1/2">
                      <div class="card p-8 mb-8">
                          <div class="flex justify-between items-center mb-6">
                              <h3 class="text-2xl font-bold">AI推荐策略</h3>
                              <span class="text-xs text-gray-400">更新于 10分钟前</span>
                          </div>
  
                          <div class="space-y-6">
                              <div class="bg-primary p-4 rounded-lg">
                                  <div class="flex justify-between items-center mb-3">
                                      <h4 class="text-lg font-semibold">平衡型投资组合</h4>
                                      <div class="flex items-center gap-1 text-warning">
                                          <i class="fas fa-star"></i>
                                          <i class="fas fa-star"></i>
                                          <i class="fas fa-star"></i>
                                          <i class="fas fa-star"></i>
                                          <i class="far fa-star"></i>
                                      </div>
                                  </div>
                                  <p class="text-gray-300 text-sm mb-4">
                                      基于当前市场状况和您的风险偏好，我们推荐一个平衡型投资组合，结合趋势跟踪和均值回归策略。
                                  </p>
                                  <div class="chart-container h-40 mb-4">
                                      <canvas id="portfolio-chart"></canvas>
                                  </div>
                                  <div class="flex justify-between text-sm">
                                      <span class="text-gray-400">预期年化收益</span>
                                      <span class="text-success font-medium">15.8%</span>
                                  </div>
                              </div>
  
                              <div class="bg-primary p-4 rounded-lg">
                                  <div class="flex justify-between items-center mb-3">
                                      <h4 class="text-lg font-semibold">BTC/ETH配对交易策略</h4>
                                      <div class="flex items-center gap-1 text-warning">
                                          <i class="fas fa-star"></i>
                                          <i class="fas fa-star"></i>
                                          <i class="fas fa-star"></i>
                                          <i class="fas fa-star-half-alt"></i>
                                          <i class="far fa-star"></i>
                                      </div>
                                  </div>
                                  <p class="text-gray-300 text-sm mb-4">
                                      利用BTC和ETH之间的价格相关性变化进行配对交易，适合当前市场波动加剧的环境。
                                  </p>
                                  <div class="chart-container h-40 mb-4">
                                      <canvas id="pair-trading-chart"></canvas>
                                  </div>
                                  <div class="flex justify-between text-sm">
                                      <span class="text-gray-400">预期年化收益</span>
                                      <span class="text-success font-medium">12.3%</span>
                                  </div>
                              </div>
  
                              <div class="bg-primary p-4 rounded-lg">
                                  <div class="flex justify-between items-center mb-3">
                                      <h4 class="text-lg font-semibold">机器学习趋势预测策略</h4>
                                      <div class="flex items-center gap-1 text-warning">
                                          <i class="fas fa-star"></i>
                                          <i class="fas fa-star"></i>
                                          <i class="fas fa-star"></i>
                                          <i class="fas fa-star"></i>
                                          <i class="fas fa-star-half-alt"></i>
                                      </div>
                                  </div>
                                  <p class="text-gray-300 text-sm mb-4">
                                      基于深度学习的趋势预测模型，结合技术指标和市场情绪分析，适合当前的趋势市场。
                                  </p>
                                  <div class="chart-container h-40 mb-4">
                                      <canvas id="ml-strategy-chart"></canvas>
                                  </div>
                                  <div class="flex justify-between text-sm">
                                      <span class="text-gray-400">预期年化收益</span>
                                      <span class="text-success font-medium">19.7%</span>
                                  </div>
                              </div>
                          </div>
                      </div>
  
                      <div class="card p-8">
                          <h3 class="text-2xl font-bold mb-6">市场洞察</h3>
                          <div class="space-y-4">
                              <div class="flex items-start gap-4">
                                  <div class="bg-secondary rounded-full p-2 mt-1">
                                      <i class="fas fa-lightbulb text-white"></i>
                                  </div>
                                  <div>
                                      <h4 class="font-semibold mb-1">市场趋势分析</h4>
                                      <p class="text-gray-300 text-sm">
                                          当前加密市场处于上升趋势，但波动性增加。BTC突破40,000美元关键阻力位，可能预示进一步上涨。
                                      </p>
                                  </div>
                              </div>
  
                              <div class="flex items-start gap-4">
                                  <div class="bg-secondary rounded-full p-2 mt-1">
                                      <i class="fas fa-chart-pie text-white"></i>
                                  </div>
                                  <div>
                                      <h4 class="font-semibold mb-1">资产配置建议</h4>
                                      <p class="text-gray-300 text-sm">
                                          建议配置：BTC (40%), ETH (30%), 大型山寨币 (20%), 稳定币 (10%)，以平衡风险和收益。
                                      </p>
                                  </div>
                              </div>
  
                              <div class="flex items-start gap-4">
                                  <div class="bg-secondary rounded-full p-2 mt-1">
                                      <i class="fas fa-exclamation-triangle text-white"></i>
                                  </div>
                                  <div>
                                      <h4 class="font-semibold mb-1">风险提示</h4>
                                      <p class="text-gray-300 text-sm">
                                          美联储可能加息，监管环境变化，以及市场情绪波动是当前主要风险因素，建议设置适当止损。
                                      </p>
                                  </div>
                              </div>
                          </div>
                      </div>
                  </div>
              </div>
          </div>
      </section>
  
      <!-- Dashboard Section -->
      <section id="dashboard" class="py-20 bg-secondary">
          <div class="container mx-auto px-4">
              <div class="text-center mb-16">
                  <h2 class="text-3xl md:text-5xl font-bold mb-4" data-lang-key="dashboard-title">用户仪表盘</h2>
                  <p class="text-xl text-gray-300 max-w-2xl mx-auto" data-lang-key="dashboard-description">
                      全面的投资组合管理和性能分析工具，帮助您跟踪和优化投资表现
                  </p>
              </div>
  
              <div class="card p-8 mb-8">
                  <div class="flex flex-col md:flex-row justify-between items-start md:items-center mb-8">
                      <div>
                          <h3 class="text-2xl font-bold mb-2">投资组合概览</h3>
                          <p class="text-gray-300">最后更新: 2023年12月15日 14:30</p>
                      </div>
                      <div class="flex gap-4 mt-4 md:mt-0">
                          <button class="btn-secondary px-4 py-2 rounded-lg text-white font-medium">
                              导出报告
                          </button>
                          <button class="btn-primary px-4 py-2 rounded-lg text-white font-medium">
                              调整配置
                          </button>
                      </div>
                  </div>
  
                  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-8">
                      <div class="dashboard-card bg-secondary-light p-6 rounded-xl">
                          <p class="text-gray-300 mb-2">总资产</p>
                          <p class="text-3xl font-bold mb-2">128,547.25 USDT</p>
                          <div class="flex items-center gap-2 text-success">
                              <i class="fas fa-arrow-up"></i>
                              <span>+8.32% 本月</span>
                          </div>
                      </div>
  
                      <div class="dashboard-card bg-secondary-light p-6 rounded-xl">
                          <p class="text-gray-300 mb-2">总收益</p>
                          <p class="text-3xl font-bold mb-2">15,632.80 USDT</p>
                          <div class="flex items-center gap-2 text-success">
                              <i class="fas fa-arrow-up"></i>
                              <span>+13.75% 年化</span>
                          </div>
                      </div>
  
                      <div class="dashboard-card bg-secondary-light p-6 rounded-xl">
                          <p class="text-gray-300 mb-2">风险评分</p>
                          <p class="text-3xl font-bold mb-2">中等</p>
                          <div class="w-full bg-gray-700 rounded-full h-2">
                              <div class="bg-warning h-2 rounded-full" style="width: 60%"></div>
                          </div>
                      </div>
  
                      <div class="dashboard-card bg-secondary-light p-6 rounded-xl">
                          <p class="text-gray-300 mb-2">活跃策略</p>
                          <p class="text-3xl font-bold mb-2">5</p>
                          <div class="flex items-center gap-2 text-gray-300">
                              <span>3个盈利中</span>
                          </div>
                      </div>
                  </div>
  
                  <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
                      <div class="lg:col-span-2">
                          <h4 class="text-xl font-semibold mb-4">投资组合表现</h4>
                          <div class="chart-container">
                              <canvas id="portfolio-performance-chart"></canvas>
                          </div>
                      </div>
  
                      <div>
                          <h4 class="text-xl font-semibold mb-4">资产配置</h4>
                          <div class="chart-container">
                              <canvas id="asset-allocation-chart"></canvas>
                          </div>
                      </div>
                  </div>
              </div>
  
              <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                  <div class="card p-8">
                      <h3 class="text-2xl font-bold mb-6">活跃策略</h3>
                      <div class="space-y-4">
                          <div class="bg-secondary-light p-4 rounded-lg">
                              <div class="flex justify-between items-center mb-2">
                                  <h4 class="font-semibold">BTC/ETH配对交易</h4>
                                  <span class="text-success">+2.4%</span>
                              </div>
                              <div class="w-full bg-gray-700 rounded-full h-2 mb-2">
                                  <div class="bg-success h-2 rounded-full" style="width: 75%"></div>
                              </div>
                              <div class="flex justify-between text-sm text-gray-400">
                                  <span>已运行 14天</span>
                                  <span>当前收益: 856.32 USDT</span>
                              </div>
                          </div>
  
                          <div class="bg-secondary-light p-4 rounded-lg">
                              <div class="flex justify-between items-center mb-2">
                                  <h4 class="font-semibold">机器学习趋势预测</h4>
                                  <span class="text-success">+4.7%</span>
                              </div>
                              <div class="w-full bg-gray-700 rounded-full h-2 mb-2">
                                  <div class="bg-success h-2 rounded-full" style="width: 85%"></div>
                              </div>
                              <div class="flex justify-between text-sm text-gray-400">
                                  <span>已运行 8天</span>
                                  <span>当前收益: 1,245.78 USDT</span>
                              </div>
                          </div>
  
                          <div class="bg-secondary-light p-4 rounded-lg">
                              <div class="flex justify-between items-center mb-2">
                                  <h4 class="font-semibold">均值回归策略</h4>
                                  <span class="text-danger">-1.2%</span>
                              </div>
                              <div class="w-full bg-gray-700 rounded-full h-2 mb-2">
                                  <div class="bg-danger h-2 rounded-full" style="width: 30%"></div>
                              </div>
                              <div class="flex justify-between text-sm text-gray-400">
                                  <span>已运行 5天</span>
                                  <span>当前收益: -324.56 USDT</span>
                              </div>
                          </div>
  
                          <div class="bg-secondary-light p-4 rounded-lg">
                              <div class="flex justify-between items-center mb-2">
                                  <h4 class="font-semibold">套利策略</h4>
                                  <span class="text-success">+0.8%</span>
                              </div>
                              <div class="w-full bg-gray-700 rounded-full h-2 mb-2">
                                  <div class="bg-success h-2 rounded-full" style="width: 60%"></div>
                              </div>
                              <div class="flex justify-between text-sm text-gray-400">
                                  <span>已运行 21天</span>
                                  <span>当前收益: 412.90 USDT</span>
                              </div>
                          </div>
  
                          <div class="bg-secondary-light p-4 rounded-lg">
                              <div class="flex justify-between items-center mb-2">
                                  <h4 class="font-semibold">多因子策略</h4>
                                  <span class="text-success">+3.1%</span>
                              </div>
                              <div class="w-full bg-gray-700 rounded-full h-2 mb-2">
                                  <div class="bg-success h-2 rounded-full" style="width: 70%"></div>
                              </div>
                              <div class="flex justify-between text-sm text-gray-400">
                                  <span>已运行 12天</span>
                                  <span>当前收益: 765.23 USDT</span>
                              </div>
                          </div>
                      </div>
                  </div>
  
                  <div class="card p-8">
                      <h3 class="text-2xl font-bold mb-6">最近交易</h3>
                      <div class="space-y-4">
                          <div class="bg-secondary-light p-4 rounded-lg">
                              <div class="flex justify-between items-center mb-2">
                                  <div class="flex items-center gap-3">
                                      <div class="w-10 h-10 rounded-full bg-primary flex items-center justify-center">
                                          <i class="fab fa-bitcoin text-yellow-500"></i>
                                      </div>
                                      <div>
                                          <h4 class="font-semibold">买入 BTC</h4>
                                          <p class="text-sm text-gray-400">机器学习趋势预测策略</p>
                                      </div>
                                  </div>
                                  <span class="text-success">+0.25 BTC</span>
                              </div>
                              <div class="flex justify-between text-sm text-gray-400">
                                  <span>2023-12-15 10:23:45</span>
                                  <span>42,567.80 USDT</span>
                              </div>
                          </div>
  
                          <div class="bg-secondary-light p-4 rounded-lg">
                              <div class="flex justify-between items-center mb-2">
                                  <div class="flex items-center gap-3">
                                      <div class="w-10 h-10 rounded-full bg-primary flex items-center justify-center">
                                          <i class="fab fa-ethereum text-blue-500"></i>
                                      </div>
                                      <div>
                                          <h4 class="font-semibold">卖出 ETH</h4>
                                          <p class="text-sm text-gray-400">BTC/ETH配对交易策略</p>
                                      </div>
                                  </div>
                                  <span class="text-danger">-1.5 ETH</span>
                              </div>
                              <div class="flex justify-between text-sm text-gray-400">
                                  <span>2023-12-15 09:12:33</span>
                                  <span>3,245.60 USDT</span>
                              </div>
                          </div>
  
                          <div class="bg-secondary-light p-4 rounded-lg">
                              <div class="flex justify-between items-center mb-2">
                                  <div class="flex items-center gap-3">
                                      <div class="w-10 h-10 rounded-full bg-primary flex items-center justify-center">
                                          <i class="fab fa-bitcoin text-yellow-500"></i>
                                      </div>
                                      <div>
                                          <h4 class="font-semibold">卖出 BTC</h4>
                                          <p class="text-sm text-gray-400">均值回归策略</p>
                                      </div>
                                  </div>
                                  <span class="text-danger">-0.15 BTC</span>
                              </div>
                              <div class="flex justify-between text-sm text-gray-400">
                                  <span>2023-12-14 16:45:12</span>
                                  <span>6,385.20 USDT</span>
                              </div>
                          </div>
  
                          <div class="bg-secondary-light p-4 rounded-lg">
                              <div class="flex justify-between items-center mb-2">
                                  <div class="flex items-center gap-3">
                                      <div class="w-10 h-10 rounded-full bg-primary flex items-center justify-center">
                                          <i class="fab fa-ethereum text-blue-500"></i>
                                      </div>
                                      <div>
                                          <h4 class="font-semibold">买入 ETH</h4>
                                          <p class="text-sm text-gray-400">多因子策略</p>
                                      </div>
                                  </div>
                                  <span class="text-success">+2.0 ETH</span>
                              </div>
                              <div class="flex justify-between text-sm text-gray-400">
                                  <span>2023-12-14 14:32:56</span>
                                  <span>4,327.80 USDT</span>
                              </div>
                          </div>
  
                          <div class="bg-secondary-light p-4 rounded-lg">
                              <div class="flex justify-between items-center mb-2">
                                  <div class="flex items-center gap-3">
                                      <div class="w-10 h-10 rounded-full bg-primary flex items-center justify-center">
                                          <i class="fab fa-solana text-purple-500"></i>
                                      </div>
                                      <div>
                                          <h4 class="font-semibold">买入 SOL</h4>
                                          <p class="text-sm text-gray-400">机器学习趋势预测策略</p>
                                      </div>
                                  </div>
                                  <span class="text-success">+15.0 SOL</span>
                              </div>
                              <div class="flex justify-between text-sm text-gray-400">
                                  <span>2023-12-13 11:05:42</span>
                                  <span>1,845.30 USDT</span>
                              </div>
                          </div>
                      </div>
                  </div>
              </div>
          </div>
      </section>
  
      <!-- About Section -->
      <section id="about" class="py-20 bg-gradient-to-b from-secondary to-secondary-light">
          <div class="container mx-auto px-4">
              <div class="text-center mb-16">
                  <h2 class="text-3xl md:text-5xl font-bold mb-4">关于我们</h2>
                  <p class="text-xl text-gray-300 max-w-2xl mx-auto">
                      CryptoBee Labs 是一家专注于加密货币量化交易的技术公司，致力于为投资者提供专业的交易工具和策略
                  </p>
              </div>
  
              <div class="flex flex-col lg:flex-row gap-12 items-center mb-16">
                  <div class="lg:w-1/2">
                      <img :src="aboutLab" alt="CryptoBee Labs" class="w-full max-w-lg rounded-xl shadow-2xl mx-auto">
                  </div>
                  <div class="lg:w-1/2">
                      <h3 class="text-2xl font-bold mb-6">我们的使命</h3>
                      <p class="text-gray-300 mb-6">
                          在快速发展的加密货币市场中，我们致力于通过先进的量化技术和人工智能算法，为投资者提供稳定、可靠的投资工具和策略，帮助他们在这个新兴市场中获取长期、可持续的收益。
                      </p>
                      <p class="text-gray-300 mb-6">
                          我们的团队由来自顶尖金融机构、科技公司和学术机构的专业人士组成，拥有丰富的量化交易、算法开发和风险管理经验。
                      </p>
                      <div class="grid grid-cols-2 gap-6">
                          <div>
                              <h4 class="font-semibold mb-2">我们的价值观</h4>
                              <ul class="space-y-2 text-gray-300">
                                  <li class="flex items-center gap-2">
                                      <i class="fas fa-check-circle text-success"></i>
                                      <span>创新与技术驱动</span>
                                  </li>
                                  <li class="flex items-center gap-2">
                                      <i class="fas fa-check-circle text-success"></i>
                                      <span>数据与科学决策</span>
                                  </li>
                                  <li class="flex items-center gap-2">
                                      <i class="fas fa-check-circle text-success"></i>
                                      <span>诚信与透明度</span>
                                  </li>
                                  <li class="flex items-center gap-2">
                                      <i class="fas fa-check-circle text-success"></i>
                                      <span>持续学习与改进</span>
                                  </li>
                              </ul>
                          </div>
                          <div>
                              <h4 class="font-semibold mb-2">我们的优势</h4>
                              <ul class="space-y-2 text-gray-300">
                                  <li class="flex items-center gap-2">
                                      <i class="fas fa-check-circle text-success"></i>
                                      <span>专业的技术团队</span>
                                  </li>
                                  <li class="flex items-center gap-2">
                                      <i class="fas fa-check-circle text-success"></i>
                                      <span>先进的算法模型</span>
                                  </li>
                                  <li class="flex items-center gap-2">
                                      <i class="fas fa-check-circle text-success"></i>
                                      <span>严格的风险管理</span>
                                  </li>
                                  <li class="flex items-center gap-2">
                                      <i class="fas fa-check-circle text-success"></i>
                                      <span>持续的研发投入</span>
                                  </li>
                              </ul>
                          </div>
                      </div>
                  </div>
              </div>
  
              <div class="card p-8 mb-16">
                  <h3 class="text-2xl font-bold mb-8 text-center">我们的团队</h3>
                  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">
                      <div class="text-center">
                          <div class="w-32 h-32 rounded-full overflow-hidden mx-auto mb-4">
                              <img :src="userMen32" alt="CEO" class="w-full h-full object-cover">
                          </div>
                          <h4 class="text-xl font-semibold mb-1">张明</h4>
                          <p class="text-accent mb-3">创始人 & CEO</p>
                          <p class="text-gray-400 text-sm">
                              前华尔街量化交易总监，拥有15年金融市场经验
                          </p>
                      </div>
  
                      <div class="text-center">
                          <div class="w-32 h-32 rounded-full overflow-hidden mx-auto mb-4">
                              <img :src="userWomen44" alt="CTO" class="w-full h-full object-cover">
                          </div>
                          <h4 class="text-xl font-semibold mb-1">李婷</h4>
                          <p class="text-accent mb-3">联合创始人 & CTO</p>
                          <p class="text-gray-400 text-sm">
                              人工智能和机器学习专家，前谷歌高级工程师
                          </p>
                      </div>
  
                      <div class="text-center">
                          <div class="w-32 h-32 rounded-full overflow-hidden mx-auto mb-4">
                              <img :src="userMen86" alt="首席科学家" class="w-full h-full object-cover">
                          </div>
                          <h4 class="text-xl font-semibold mb-1">王强</h4>
                          <p class="text-accent mb-3">首席科学家</p>
                          <p class="text-gray-400 text-sm">
                              金融工程博士，专注于量化策略和风险管理
                          </p>
                      </div>
  
                      <div class="text-center">
                          <div class="w-32 h-32 rounded-full overflow-hidden mx-auto mb-4">
                              <img :src="userWomen66" alt="首席运营官" class="w-full h-full object-cover">
                          </div>
                          <h4 class="text-xl font-semibold mb-1">陈静</h4>
                          <p class="text-accent mb-3">首席运营官</p>
                          <p class="text-gray-400 text-sm">
                              前金融科技公司高管，拥有丰富的运营和客户服务经验
                          </p>
                      </div>
                  </div>
              </div>
  
              <div class="text-center">
                  <h3 class="text-2xl font-bold mb-6">加入我们</h3>
                  <p class="text-xl text-gray-300 max-w-2xl mx-auto mb-8">
                      我们正在寻找热爱技术和金融的人才加入团队，一起推动加密货币量化交易的发展
                  </p>
                  <button class="btn-primary px-8 py-4 rounded-lg text-white font-medium text-lg">
                      查看职位
                  </button>
              </div>
          </div>
      </section>
  
      <!-- Contact Section -->
      <section id="contact" class="py-20 bg-secondary-light">
          <div class="container mx-auto px-4">
              <div class="text-center mb-16">
                  <h2 class="text-3xl md:text-5xl font-bold mb-4">联系我们</h2>
                  <p class="text-xl text-gray-300 max-w-2xl mx-auto">
                      如果您有任何问题或建议，请随时与我们联系
                  </p>
              </div>
  
              <div class="flex flex-col lg:flex-row gap-12">
                  <div class="lg:w-1/2">
                      <div class="card p-8 h-full">
                          <h3 class="text-2xl font-bold mb-6">发送消息</h3>
                          <form>
                              <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
                                  <div>
                                      <label class="block text-gray-300 mb-2">姓名</label>
                                      <input type="text" class="w-full bg-primary border border-gray-700 rounded-lg p-3 text-white" placeholder="您的姓名">
                                  </div>
                                  <div>
                                      <label class="block text-gray-300 mb-2">邮箱</label>
                                      <input type="email" class="w-full bg-primary border border-gray-700 rounded-lg p-3 text-white" placeholder="您的邮箱">
                                  </div>
                              </div>
  
                              <div class="mb-6">
                                  <label class="block text-gray-300 mb-2">主题</label>
                                  <input type="text" class="w-full bg-primary border border-gray-700 rounded-lg p-3 text-white" placeholder="消息主题">
                              </div>
  
                              <div class="mb-6">
                                  <label class="block text-gray-300 mb-2">消息</label>
                                  <textarea class="w-full bg-primary border border-gray-700 rounded-lg p-3 h-32 text-white" placeholder="请输入您的消息"></textarea>
                              </div>
  
                              <button type="submit" class="btn-primary w-full py-3 rounded-lg text-white font-medium">
                                  发送消息
                              </button>
                          </form>
                      </div>
                  </div>
  
                  <div class="lg:w-1/2">
                      <div class="card p-8 mb-8">
                          <h3 class="text-2xl font-bold mb-6">联系方式</h3>
                          <div class="space-y-4">
                              <div class="flex items-start gap-4">
                                  <div class="bg-primary rounded-full p-3 mt-1">
                                      <i class="fas fa-map-marker-alt text-white"></i>
                                  </div>
                                  <div>
                                      <h4 class="font-semibold mb-1">地址</h4>
                                      <p class="text-gray-300">
                                          北京市朝阳区建国路88号<br>
                                          现代城SOHO B座 25层
                                      </p>
                                  </div>
                              </div>
  
                              <div class="flex items-start gap-4">
                                  <div class="bg-primary rounded-full p-3 mt-1">
                                      <i class="fas fa-envelope text-white"></i>
                                  </div>
                                  <div>
                                      <h4 class="font-semibold mb-1">邮箱</h4>
                                      <p class="text-gray-300">
                                          info@cryptobeelabs.com<br>
                                          support@cryptobeelabs.com
                                      </p>
                                  </div>
                              </div>
  
                              <div class="flex items-start gap-4">
                                  <div class="bg-primary rounded-full p-3 mt-1">
                                      <i class="fas fa-phone-alt text-white"></i>
                                  </div>
                                  <div>
                                      <h4 class="font-semibold mb-1">电话</h4>
                                      <p class="text-gray-300">
                                          +86 10 8888 8888<br>
                                          +86 10 8888 9999
                                      </p>
                                  </div>
                              </div>
                          </div>
                      </div>
  
                      <div class="card p-8">
                          <h3 class="text-2xl font-bold mb-6">关注我们</h3>
                          <div class="flex gap-4">
                              <a href="#" class="bg-primary hover:bg-primary-light transition-colors w-12 h-12 rounded-full flex items-center justify-center">
                                  <i class="fab fa-twitter text-white"></i>
                              </a>
                              <a href="#" class="bg-primary hover:bg-primary-light transition-colors w-12 h-12 rounded-full flex items-center justify-center">
                                  <i class="fab fa-linkedin-in text-white"></i>
                              </a>
                              <a href="#" class="bg-primary hover:bg-primary-light transition-colors w-12 h-12 rounded-full flex items-center justify-center">
                                  <i class="fab fa-telegram-plane text-white"></i>
                              </a>
                              <a href="#" class="bg-primary hover:bg-primary-light transition-colors w-12 h-12 rounded-full flex items-center justify-center">
                                  <i class="fab fa-medium-m text-white"></i>
                              </a>
                              <a href="#" class="bg-primary hover:bg-primary-light transition-colors w-12 h-12 rounded-full flex items-center justify-center">
                                  <i class="fab fa-github text-white"></i>
                              </a>
                          </div>
                      </div>
                  </div>
              </div>
          </div>
      </section>
  
      <!-- Footer -->
      <footer class="bg-primary py-12">
          <div class="container mx-auto px-4">
              <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 mb-12">
                  <div>
                      <div class="flex items-center gap-2 mb-6">
                          <img :src="logoPrimary" alt="CryptoBee Labs Logo" class="h-10 w-auto">
                          <div>
                      <span class="text-xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-white to-accent-light">CryptoBee Labs</span>
                      <p class="text-xs text-gray-400">Bee the win</p>
                  </div>
                      </div>
                      <p class="text-gray-400 mb-6">
                          专业的加密货币量化交易工具和策略提供商，帮助投资者在数字资产市场中获取稳定收益。
                      </p>
                      <div class="flex gap-4">
                          <a href="#" class="text-gray-400 hover:text-white transition-colors">
                              <i class="fab fa-twitter"></i>
                          </a>
                          <a href="#" class="text-gray-400 hover:text-white transition-colors">
                              <i class="fab fa-linkedin-in"></i>
                          </a>
                          <a href="#" class="text-gray-400 hover:text-white transition-colors">
                              <i class="fab fa-telegram-plane"></i>
                          </a>
                          <a href="#" class="text-gray-400 hover:text-white transition-colors">
                              <i class="fab fa-medium-m"></i>
                          </a>
                      </div>
                  </div>
  
                  <div>
                      <h4 class="text-lg font-semibold mb-6">产品</h4>
                      <ul class="space-y-3">
                          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">QuantStrategy Pro</a></li>
                          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">AI Advisor</a></li>
                          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">DataHub</a></li>
                          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">风险管理工具</a></li>
                          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">API服务</a></li>
                      </ul>
                  </div>
  
                  <div>
                      <h4 class="text-lg font-semibold mb-6">资源</h4>
                      <ul class="space-y-3">
                          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">文档中心</a></li>
                          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">API文档</a></li>
                          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">策略库</a></li>
                          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">博客</a></li>
                          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">帮助中心</a></li>
                      </ul>
                  </div>
  
                  <div>
                      <h4 class="text-lg font-semibold mb-6">公司</h4>
                      <ul class="space-y-3">
                          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">关于我们</a></li>
                          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">团队</a></li>
                          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">招贤纳士</a></li>
                          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">联系我们</a></li>
                          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">媒体资源</a></li>
                      </ul>
                  </div>
              </div>
  
              <div class="border-t border-gray-800 pt-8">
                  <div class="flex flex-col md:flex-row justify-between items-center">
                      <p class="text-gray-400 mb-4 md:mb-0">
                          &copy; 2023 CryptoBee Labs. 保留所有权利。
                      </p>
                      <div class="flex gap-6">
                          <a href="#" class="text-gray-400 hover:text-white transition-colors">隐私政策</a>
                          <a href="#" class="text-gray-400 hover:text-white transition-colors">服务条款</a>
                          <a href="#" class="text-gray-400 hover:text-white transition-colors">Cookie政策</a>
                      </div>
                  </div>
              </div>
          </div>
      </footer>
  
      <!-- Back to Top Button -->
      <button id="back-to-top" class="fixed bottom-8 right-8 bg-secondary hover:bg-secondary-light transition-colors w-12 h-12 rounded-full flex items-center justify-center shadow-lg opacity-0 invisible">
          <i class="fas fa-arrow-up text-white"></i>
      </button>
  </div>
</template>

<script setup>
import { onBeforeUnmount, onMounted } from 'vue'
import Chart from 'chart.js/auto'
import * as THREE from 'three'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'

import logoPrimary from './assets/images/logo-primary.png'
import logoCompact from './assets/images/logo-compact.png'
import heroDashboard from './assets/images/hero-dashboard.png'
import aboutLab from './assets/images/about-lab.png'
import userMen32 from './assets/images/user-men-32.jpg'
import userWomen44 from './assets/images/user-women-44.jpg'
import userMen86 from './assets/images/user-men-86.jpg'
import userWomen66 from './assets/images/user-women-66.jpg'

const translations = {
  'zh-CN': {
    home: '首页',
    products: '产品',
    strategies: '策略',
    'ai-system': 'AI系统',
    dashboard: '仪表盘',
    about: '关于我们',
    login: '登录',
    register: '注册',
    language: '语言',
    'hero-title': '智能量化交易',
    'hero-subtitle': '加密资产的未来',
    'hero-description': 'CryptoBee Labs 提供专业的加密货币量化交易工具和策略，帮助投资者在数字资产市场中获取稳定收益。',
    'hero-cta-1': '开始使用',
    'hero-cta-2': '观看演示',
    'products-title': '我们的产品',
    'products-description': '为加密货币投资者提供全方位的量化交易工具和解决方案',
    'strategies-title': '量化策略',
    'strategies-description': '基于先进的数学模型和算法，我们的策略帮助投资者在不同市场环境中获取稳定收益',
    'ai-system-title': '智能策略推荐系统',
    'ai-system-description': '基于人工智能的策略推荐系统，根据市场状况和用户风险偏好，实时生成个性化投资建议',
    'dashboard-title': '用户仪表盘',
    'dashboard-description': '全面的投资组合管理和性能分析工具，帮助您跟踪和优化投资表现',
    'about-title': '关于我们',
    'about-description': 'CryptoBee Labs 是一家专注于加密货币量化交易的技术公司，致力于为投资者提供先进的交易工具和策略'
  },
  'zh-TW': {
    home: '首頁',
    products: '產品',
    strategies: '策略',
    'ai-system': 'AI系統',
    dashboard: '儀表板',
    about: '關於我們',
    login: '登入',
    register: '註冊',
    language: '語言',
    'hero-title': '智能量化交易',
    'hero-subtitle': '加密資產的未來',
    'hero-description': 'CryptoBee Labs 提供專業的加密貨幣量化交易工具和策略，幫助投資者在數字資產市場中獲取穩定收益。',
    'hero-cta-1': '開始使用',
    'hero-cta-2': '觀看演示',
    'products-title': '我們的產品',
    'products-description': '為加密貨幣投資者提供全方位的量化交易工具和解決方案',
    'strategies-title': '量化策略',
    'strategies-description': '基於先進的數學模型和算法，我們的策略幫助投資者在不同市場環境中獲取穩定收益',
    'ai-system-title': '智能策略推薦系統',
    'ai-system-description': '基於人工智能的策略推薦系統，根據市場狀況和用戶風險偏好，實時生成個性化投資建議',
    'dashboard-title': '用戶儀表板',
    'dashboard-description': '全面的投資組合管理和性能分析工具，幫助您跟蹤和優化投資表現',
    'about-title': '關於我們',
    'about-description': 'CryptoBee Labs 是一家專注於加密貨幣量化交易的技術公司，致力於為投資者提供先進的交易工具和策略'
  },
  en: {
    home: 'Home',
    products: 'Products',
    strategies: 'Strategies',
    'ai-system': 'AI System',
    dashboard: 'Dashboard',
    about: 'About Us',
    login: 'Login',
    register: 'Register',
    language: 'Language',
    'hero-title': 'Intelligent Quantitative Trading',
    'hero-subtitle': 'The Future of Crypto Assets',
    'hero-description': 'CryptoBee Labs provides professional cryptocurrency quantitative trading tools and strategies to help investors achieve stable returns in the digital asset market.',
    'hero-cta-1': 'Get Started',
    'hero-cta-2': 'Watch Demo',
    'products-title': 'Our Products',
    'products-description': 'Comprehensive quantitative trading tools and solutions for cryptocurrency investors',
    'strategies-title': 'Quantitative Strategies',
    'strategies-description': 'Based on advanced mathematical models and algorithms, our strategies help investors achieve stable returns in different market environments',
    'ai-system-title': 'Intelligent Strategy Recommendation System',
    'ai-system-description': 'AI-driven strategy recommendation system that generates personalized investment advice based on market conditions and user risk preferences',
    'dashboard-title': 'User Dashboard',
    'dashboard-description': 'Comprehensive portfolio management and performance analysis tools to help you track and optimize your investment performance',
    'about-title': 'About Us',
    'about-description': 'CryptoBee Labs is a technology company focused on cryptocurrency quantitative trading, dedicated to providing investors with advanced trading tools and strategies'
  }
}

const languageLabels = {
  'zh-CN': '中文简体',
  'zh-TW': '中文繁体',
  en: 'English'
}

const strategyLibrary = {
  'mean-reversion': {
    title: '均值回归策略',
    description:
      '均值回归策略基于市场价格会围绕其平均值波动的假设，当价格偏离均值较远时，预期会向均值回归。该策略适合震荡市场环境，在价格大幅波动时捕捉反转机会。',
    params: [
      { label: '均值周期', value: '20天' },
      { label: '标准差倍数', value: '2.0' },
      { label: '持仓周期', value: '3-5天' },
      { label: '止损比例', value: '5%' }
    ],
    marketConditions: [
      { label: '市场波动性适中', status: 'success' },
      { label: '无明显趋势方向', status: 'success' },
      { label: '强烈单边趋势市场', status: 'danger' },
      { label: '极端市场情绪期间', status: 'danger' }
    ]
  },
  momentum: {
    title: '动量策略',
    description:
      '动量策略基于市场趋势的持续性，认为价格上涨的资产在短期内会继续上涨，价格下跌的资产在短期内会继续下跌。该策略适合明显趋势的市场环境。',
    params: [
      { label: '动量周期', value: '14天' },
      { label: '确认周期', value: '5天' },
      { label: '持仓周期', value: '7-14天' },
      { label: '止损比例', value: '8%' }
    ],
    marketConditions: [
      { label: '明显的市场趋势', status: 'success' },
      { label: '高流动性市场', status: 'success' },
      { label: '震荡市场', status: 'danger' },
      { label: '市场转折点', status: 'danger' }
    ]
  },
  arbitrage: {
    title: '套利策略',
    description:
      '套利策略利用不同市场或交易对之间的价格差异进行交易，通过同时买入低价资产和卖出高价资产，在价格收敛时获取无风险收益。',
    params: [
      { label: '价差阈值', value: '0.5%' },
      { label: '最大持仓时间', value: '24小时' },
      { label: '最小利润', value: '0.3%' },
      { label: '资金分配', value: '20%' }
    ],
    marketConditions: [
      { label: '市场间价格差异', status: 'success' },
      { label: '高流动性', status: 'success' },
      { label: '市场极端波动', status: 'danger' },
      { label: '交易所技术问题', status: 'danger' }
    ]
  },
  'ml-based': {
    title: '机器学习策略',
    description:
      '基于深度学习的预测模型，通过分析大量历史数据和市场特征，预测资产价格走势。该策略能够适应不同的市场环境，自动学习和优化。',
    params: [
      { label: '模型类型', value: 'LSTM神经网络' },
      { label: '预测周期', value: '1-24小时' },
      { label: '训练数据', value: '过去1年' },
      { label: '更新频率', value: '每周' }
    ],
    marketConditions: [
      { label: '数据充足的市场', status: 'success' },
      { label: '中等波动性', status: 'success' },
      { label: '极端市场事件', status: 'danger' },
      { label: '市场结构变化', status: 'danger' }
    ]
  },
  'multi-factor': {
    title: '多因子策略',
    description:
      '多因子策略综合考虑多种市场因素，如价值、动量、波动性等，构建投资组合。通过权重优化，在不同市场环境下获取稳定收益。',
    params: [
      { label: '因子数量', value: '8-12个' },
      { label: '再平衡频率', value: '每周' },
      { label: '因子权重', value: '动态调整' },
      { label: '风险控制', value: 'VaR模型' }
    ],
    marketConditions: [
      { label: '多元化市场', status: 'success' },
      { label: '中等波动性', status: 'success' },
      { label: '单一主导因素市场', status: 'danger' },
      { label: '极端相关性环境', status: 'danger' }
    ]
  }
}

const strategyPerformanceData = {
  'mean-reversion': {
    strategy: [100, 102, 105, 103, 107, 110, 108, 112, 115, 113, 118, 125],
    benchmark: [100, 101, 103, 102, 104, 105, 106, 107, 108, 109, 110, 112]
  },
  momentum: {
    strategy: [100, 103, 107, 110, 112, 115, 113, 116, 120, 123, 125, 128],
    benchmark: [100, 101, 103, 102, 104, 105, 106, 107, 108, 109, 110, 112]
  },
  arbitrage: {
    strategy: [100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 113],
    benchmark: [100, 101, 103, 102, 104, 105, 106, 107, 108, 109, 110, 112]
  },
  'ml-based': {
    strategy: [100, 104, 108, 106, 110, 115, 118, 120, 122, 125, 128, 132],
    benchmark: [100, 101, 103, 102, 104, 105, 106, 107, 108, 109, 110, 112]
  },
  'multi-factor': {
    strategy: [100, 102, 105, 107, 110, 112, 115, 117, 120, 122, 124, 127],
    benchmark: [100, 101, 103, 102, 104, 105, 106, 107, 108, 109, 110, 112]
  }
}

const cleanupFns = []
const chartInstances = new Map()
let gsapContext

gsap.registerPlugin(ScrollTrigger)

function changeLanguage(lang) {
  const locale = translations[lang] ? lang : 'zh-CN'
  document.documentElement.lang = locale
  const languageDisplay = document.getElementById('current-language')
  if (languageDisplay) {
    languageDisplay.textContent = languageLabels[locale] ?? languageLabels['zh-CN']
  }

  document.querySelectorAll('[data-lang-key]').forEach((el) => {
    const key = el.getAttribute('data-lang-key')
    if (key && translations[locale][key]) {
      el.textContent = translations[locale][key]
    }
  })

  document.querySelectorAll('[data-lang]').forEach((btn) => {
    if (btn.getAttribute('data-lang') === locale) {
      btn.classList.add('bg-primary-light')
      btn.classList.remove('bg-primary')
    } else {
      btn.classList.remove('bg-primary-light')
      btn.classList.add('bg-primary')
    }
  })

  localStorage.setItem('preferredLanguage', locale)
}

function initLanguageSwitcher() {
  const buttons = Array.from(document.querySelectorAll('[data-lang]'))
  if (!buttons.length) {
    return () => {}
  }

  const handleClick = (event) => {
    const lang = event.currentTarget.getAttribute('data-lang')
    if (lang && translations[lang]) {
      changeLanguage(lang)
    }
  }

  buttons.forEach((btn) => btn.addEventListener('click', handleClick))

  const savedLang = localStorage.getItem('preferredLanguage')
  changeLanguage(translations[savedLang] ? savedLang : 'zh-CN')

  return () => {
    buttons.forEach((btn) => btn.removeEventListener('click', handleClick))
  }
}

function initMobileMenu() {
  const menuButton = document.getElementById('mobile-menu-button')
  const closeButton = document.getElementById('close-menu-button')
  const menu = document.getElementById('mobile-menu')

  if (!menuButton || !closeButton || !menu) {
    return () => {}
  }

  const openMenu = () => menu.classList.add('open')
  const closeMenu = () => menu.classList.remove('open')

  menuButton.addEventListener('click', openMenu)
  closeButton.addEventListener('click', closeMenu)
  const links = Array.from(menu.querySelectorAll('a'))
  links.forEach((link) => link.addEventListener('click', closeMenu))

  return () => {
    menuButton.removeEventListener('click', openMenu)
    closeButton.removeEventListener('click', closeMenu)
    links.forEach((link) => link.removeEventListener('click', closeMenu))
  }
}

function initBackToTop() {
  const button = document.getElementById('back-to-top')
  if (!button) {
    return () => {}
  }

  const toggleVisibility = () => {
    if (window.pageYOffset > 300) {
      button.classList.remove('opacity-0', 'invisible')
      button.classList.add('opacity-100', 'visible')
    } else {
      button.classList.remove('opacity-100', 'visible')
      button.classList.add('opacity-0', 'invisible')
    }
  }

  const scrollHandler = () => toggleVisibility()
  const clickHandler = () => {
    window.scrollTo({
      top: 0,
      behavior: 'smooth'
    })
  }

  window.addEventListener('scroll', scrollHandler)
  button.addEventListener('click', clickHandler)
  toggleVisibility()

  return () => {
    window.removeEventListener('scroll', scrollHandler)
    button.removeEventListener('click', clickHandler)
  }
}

function initStrategySelection() {
  const cards = Array.from(document.querySelectorAll('.strategy-card'))
  if (!cards.length) {
    return () => {}
  }

  const handleClick = (event) => {
    const target = event.currentTarget
    cards.forEach((card) => card.classList.remove('active'))
    target.classList.add('active')
    const strategyType = target.getAttribute('data-strategy') ?? 'mean-reversion'
    updateStrategyDetails(strategyType)
  }

  cards.forEach((card) => card.addEventListener('click', handleClick))
  const initialType = cards[0]?.getAttribute('data-strategy') ?? 'mean-reversion'
  updateStrategyDetails(initialType)

  return () => {
    cards.forEach((card) => card.removeEventListener('click', handleClick))
  }
}

function updateStrategyDetails(strategyType) {
  const container = document.getElementById('strategy-details')
  const strategy = strategyLibrary[strategyType] ?? strategyLibrary['mean-reversion']

  if (!container) {
    return
  }

  const paramsHTML = strategy.params
    .map(
      (param) => `
        <li class="flex justify-between">
          <span class="text-gray-400">${param.label}</span>
          <span>${param.value}</span>
        </li>
      `
    )
    .join('')

  const conditionsHTML = strategy.marketConditions
    .map(
      (condition) => `
        <div class="flex items-center gap-3">
          <div class="w-3 h-3 rounded-full bg-${condition.status}"></div>
          <span>${condition.label}</span>
        </div>
      `
    )
    .join('')

  container.innerHTML = `
    <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
      <div>
        <h4 class="text-xl font-semibold mb-4">${strategy.title}</h4>
        <p class="text-gray-300 mb-6">${strategy.description}</p>
        <h5 class="text-lg font-semibold mb-3">核心参数</h5>
        <ul class="space-y-2 mb-6">
          ${paramsHTML}
        </ul>
      </div>
      <div>
        <h5 class="text-lg font-semibold mb-3">适用市场条件</h5>
        <div class="space-y-4 mb-6">
          ${conditionsHTML}
        </div>
        <button class="btn-primary w-full py-3 rounded-lg text-white font-medium">
          应用此策略
        </button>
      </div>
    </div>
  `

  updateBacktestChart(strategyType)
}

function updateMetricValue(metric, value) {
  const valueEl = document.querySelector(`[data-metric="${metric}"] .metric-value`)
  if (valueEl) {
    valueEl.textContent = value
  }
}

function updateBacktestChart(strategyType = 'mean-reversion') {
  const dataset = strategyPerformanceData[strategyType] ?? strategyPerformanceData['mean-reversion']
  const chart = chartInstances.get('backtest-chart')

  if (!chart) {
    return
  }

  chart.data.datasets[0].data = dataset.strategy
  chart.data.datasets[1].data = dataset.benchmark
  chart.update()

  const lastValue = dataset.strategy[dataset.strategy.length - 1]
  const annualReturn = ((lastValue / dataset.strategy[0]) - 1) * 100
  const maxDrawdown = calculateMaxDrawdown(dataset.strategy)
  const sharpeRatio = ((annualReturn / 10) * 1.5).toFixed(2)
  const winRate = (60 + Math.random() * 15).toFixed(1)

  updateMetricValue('annualReturn', `+${annualReturn.toFixed(1)}%`)
  updateMetricValue('maxDrawdown', `-${maxDrawdown.toFixed(1)}%`)
  updateMetricValue('sharpe', sharpeRatio)
  updateMetricValue('winRate', `${winRate}%`)
}

function calculateMaxDrawdown(data) {
  let maxDrawdown = 0
  let peak = data[0]

  data.forEach((value) => {
    if (value > peak) {
      peak = value
    } else {
      const drawdown = ((peak - value) / peak) * 100
      maxDrawdown = Math.max(maxDrawdown, drawdown)
    }
  })

  return maxDrawdown
}

function initCharts() {
  destroyCharts()

  const lineScaleOptions = (showXGrid = true) => ({
    x: {
      grid: {
        color: showXGrid ? 'rgba(255, 255, 255, 0.1)' : undefined,
        display: showXGrid
      },
      ticks: {
        color: '#9CA3AF'
      }
    },
    y: {
      grid: {
        color: 'rgba(255, 255, 255, 0.1)'
      },
      ticks: {
        color: '#9CA3AF'
      }
    }
  })

  const configs = [
    {
      id: 'backtest-chart',
      config: {
        type: 'line',
        data: {
          labels: ['1月', '2月', '3月', '4月', '5月', '6月', '7月', '8月', '9月', '10月', '11月', '12月'],
          datasets: [
            {
              label: '策略收益',
              data: strategyPerformanceData['mean-reversion'].strategy,
              borderColor: '#A367B1',
              backgroundColor: 'rgba(163, 103, 177, 0.1)',
              borderWidth: 2,
              fill: true,
              tension: 0.4
            },
            {
              label: '基准收益',
              data: strategyPerformanceData['mean-reversion'].benchmark,
              borderColor: '#6B7280',
              borderWidth: 2,
              borderDash: [5, 5],
              fill: false,
              tension: 0.4
            }
          ]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: {
            legend: {
              position: 'top',
              labels: {
                color: '#F8FAFC'
              }
            },
            tooltip: {
              mode: 'index',
              intersect: false
            }
          },
          scales: lineScaleOptions()
        }
      }
    },
    {
      id: 'portfolio-chart',
      config: {
        type: 'line',
        data: {
          labels: ['1月', '2月', '3月', '4月', '5月', '6月'],
          datasets: [
            {
              label: '平衡型投资组合',
              data: [100, 105, 103, 108, 112, 115],
              borderColor: '#A367B1',
              backgroundColor: 'rgba(163, 103, 177, 0.1)',
              borderWidth: 2,
              fill: true,
              tension: 0.4
            }
          ]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: {
            legend: {
              display: false
            }
          },
          scales: lineScaleOptions(false)
        }
      }
    },
    {
      id: 'pair-trading-chart',
      config: {
        type: 'line',
        data: {
          labels: ['1月', '2月', '3月', '4月', '5月', '6月'],
          datasets: [
            {
              label: 'BTC/ETH配对',
              data: [100, 102, 101, 104, 103, 106],
              borderColor: '#5B0888',
              backgroundColor: 'rgba(91, 8, 136, 0.1)',
              borderWidth: 2,
              fill: true,
              tension: 0.4
            }
          ]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: {
            legend: {
              display: false
            }
          },
          scales: lineScaleOptions(false)
        }
      }
    },
    {
      id: 'ml-strategy-chart',
      config: {
        type: 'line',
        data: {
          labels: ['1月', '2月', '3月', '4月', '5月', '6月'],
          datasets: [
            {
              label: '机器学习策略',
              data: [100, 104, 108, 106, 112, 120],
              borderColor: '#713ABE',
              backgroundColor: 'rgba(113, 58, 190, 0.1)',
              borderWidth: 2,
              fill: true,
              tension: 0.4
            }
          ]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: {
            legend: {
              display: false
            }
          },
          scales: lineScaleOptions(false)
        }
      }
    },
    {
      id: 'portfolio-performance-chart',
      config: {
        type: 'line',
        data: {
          labels: ['1月', '2月', '3月', '4月', '5月', '6月', '7月', '8月', '9月', '10月', '11月', '12月'],
          datasets: [
            {
              label: '投资组合',
              data: [100, 105, 103, 108, 112, 110, 115, 118, 120, 118, 122, 128],
              borderColor: '#A367B1',
              backgroundColor: 'rgba(163, 103, 177, 0.1)',
              borderWidth: 2,
              fill: true,
              tension: 0.4
            },
            {
              label: 'BTC',
              data: [100, 102, 105, 103, 106, 108, 110, 112, 115, 113, 116, 120],
              borderColor: '#F7931A',
              borderWidth: 2,
              fill: false,
              tension: 0.4
            },
            {
              label: 'ETH',
              data: [100, 104, 102, 106, 110, 108, 112, 115, 113, 117, 120, 125],
              borderColor: '#627EEA',
              borderWidth: 2,
              fill: false,
              tension: 0.4
            }
          ]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: {
            legend: {
              position: 'top',
              labels: {
                color: '#F8FAFC'
              }
            },
            tooltip: {
              mode: 'index',
              intersect: false
            }
          },
          scales: lineScaleOptions()
        }
      }
    },
    {
      id: 'asset-allocation-chart',
      config: {
        type: 'doughnut',
        data: {
          labels: ['BTC', 'ETH', 'SOL', 'ADA', '其他', '稳定币'],
          datasets: [
            {
              data: [40, 25, 10, 8, 7, 10],
              backgroundColor: ['#F7931A', '#627EEA', '#00FFA3', '#0066FF', '#A367B1', '#8B5CF6'],
              borderWidth: 0
            }
          ]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: {
            legend: {
              position: 'bottom',
              labels: {
                color: '#F8FAFC',
                padding: 15,
                usePointStyle: true,
                pointStyle: 'circle'
              }
            }
          },
          cutout: '70%'
        }
      }
    }
  ]

  configs.forEach(({ id, config }) => {
    const canvas = document.getElementById(id)
    if (canvas) {
      const context = canvas.getContext('2d')
      const chart = new Chart(context, config)
      chartInstances.set(id, chart)
    }
  })

  updateBacktestChart('mean-reversion')

  return () => {
    destroyCharts()
  }
}

function destroyCharts() {
  chartInstances.forEach((chart) => chart.destroy())
  chartInstances.clear()
}

function initThreeScene() {
  const canvas = document.getElementById('hero-canvas')
  if (!canvas) {
    return () => {}
  }

  const scene = new THREE.Scene()
  const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000)
  const renderer = new THREE.WebGLRenderer({
    canvas,
    alpha: true,
    antialias: true
  })

  renderer.setSize(window.innerWidth, window.innerHeight)
  renderer.setPixelRatio(window.devicePixelRatio)

  const particlesGeometry = new THREE.BufferGeometry()
  const particlesCount = 1500
  const positions = new Float32Array(particlesCount * 3)
  for (let i = 0; i < particlesCount * 3; i += 1) {
    positions[i] = (Math.random() - 0.5) * 10
  }

  particlesGeometry.setAttribute('position', new THREE.BufferAttribute(positions, 3))
  const particlesMaterial = new THREE.PointsMaterial({
    size: 0.02,
    color: 0xa367b1,
    transparent: true,
    opacity: 0.8
  })

  const particlesMesh = new THREE.Points(particlesGeometry, particlesMaterial)
  scene.add(particlesMesh)

  const ambientLight = new THREE.AmbientLight(0xffffff, 0.5)
  scene.add(ambientLight)
  const pointLight = new THREE.PointLight(0xA367B1, 0.5)
  pointLight.position.set(2, 3, 4)
  scene.add(pointLight)

  camera.position.z = 5

  let animationFrame
  const animate = () => {
    animationFrame = requestAnimationFrame(animate)
    particlesMesh.rotation.y += 0.001
    particlesMesh.rotation.x += 0.0005
    renderer.render(scene, camera)
  }

  animate()

  const handleResize = () => {
    camera.aspect = window.innerWidth / window.innerHeight
    camera.updateProjectionMatrix()
    renderer.setSize(window.innerWidth, window.innerHeight)
  }

  window.addEventListener('resize', handleResize)

  return () => {
    cancelAnimationFrame(animationFrame)
    window.removeEventListener('resize', handleResize)
    particlesGeometry.dispose()
    particlesMaterial.dispose()
    renderer.dispose()
  }
}

function initGsapAnimations() {
  gsapContext = gsap.context(() => {
    gsap.from('.hero-content h1', {
      opacity: 0,
      y: 50,
      duration: 1,
      delay: 0.5
    })

    gsap.from('.hero-content p', {
      opacity: 0,
      y: 30,
      duration: 1,
      delay: 0.8
    })

    gsap.from('.hero-content .flex', {
      opacity: 0,
      y: 30,
      duration: 1,
      delay: 1.1
    })

    gsap.utils.toArray('.card').forEach((card, index) => {
      gsap.from(card, {
        scrollTrigger: {
          trigger: card,
          start: 'top bottom-=100',
          toggleActions: 'play none none none'
        },
        opacity: 0,
        y: 50,
        duration: 0.8,
        delay: index * 0.1
      })
    })

    gsap.utils.toArray('.feature-icon').forEach((icon, index) => {
      gsap.from(icon, {
        scrollTrigger: {
          trigger: icon,
          start: 'top bottom-=100',
          toggleActions: 'play none none none'
        },
        opacity: 0,
        scale: 0.5,
        duration: 0.5,
        delay: index * 0.1
      })
    })
  })

  return () => {
    gsapContext?.revert()
    gsapContext = undefined
  }
}

onMounted(() => {
  cleanupFns.push(initLanguageSwitcher())
  cleanupFns.push(initMobileMenu())
  cleanupFns.push(initBackToTop())
  cleanupFns.push(initCharts())
  cleanupFns.push(initStrategySelection())
  cleanupFns.push(initThreeScene())
  cleanupFns.push(initGsapAnimations())
})

onBeforeUnmount(() => {
  cleanupFns.forEach((fn) => typeof fn === 'function' && fn())
  cleanupFns.length = 0
})
</script>
