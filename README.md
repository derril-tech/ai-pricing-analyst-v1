# 🤖 LangGraph Pricing Analyst
**with OpenAI SDK**

🌐 **See the Live Application**: [https://web-for-price-analyst-production.up.railway.app/](https://web-for-price-analyst-production.up.railway.app/)

> **AI-powered pricing intelligence that fuses Stripe revenue data with competitor benchmarks to suggest optimal prices with clear explanations.** ⚡

---

## ✨ Features

### 🎯 **Core Functionality**
- 🤖 **LangGraph-Powered AI** - Multi-agent pricing analysis using LangGraph's DAG architecture
- 💰 **Stripe Integration** - Real-time revenue metrics and product pricing from Stripe (test mode)
- 🏪 **Competitor Analysis** - Fetches and analyzes competitor pricing from external API
- 🎯 **Smart Recommendations** - AI-generated pricing suggestions with confidence scores
- 📊 **Visual Dashboard** - SKU pricing overview with KPIs and comparative analysis
- 🎮 **Interactive Playground** - Run custom pricing scenarios and get instant AI feedback

### 🎨 **Beautiful UI/UX**
- ✨ **Modern 2025 Design** - Glassmorphism, gradients, micro-animations, video backgrounds
- 🌙 **Dark Mode Default** - Full dark mode support with smooth transitions (default theme)
- 📱 **Fully Responsive** - Optimized for desktop, tablet, and mobile devices
- ♿ **Accessible** - WCAG AA compliant with keyboard navigation
- 🎯 **Intuitive Interface** - Clean, user-friendly design with contextual suggestions

### 📊 **Dashboard Features**
- 📈 **KPI Cards** - Total SKUs, average confidence, agent runs
- 📝 **SKU Pricing Table** - Compare current price vs AI recommendation vs competitor median
- 🔍 **Search & Filter** - Filter by SKU name, confidence range, price range, trends
- 💹 **Price Simulator** - Interactive tool to test price changes and see revenue impact
- 📉 **Price Curve Chart** - Visual representation of optimal price ranges
- 📤 **Export Options** - Export analysis as PDF, CSV, or shareable links
- 🔄 **Live Updates** - Real-time polling for new agent runs and recommendations

### 🚀 **Advanced Features**
- 🎯 **LangGraph Pipeline** - Multi-node analysis: Fetch → Compare → Suggest
- 📊 **Confidence Scoring** - AI-provided confidence levels for each recommendation
- 💾 **Persistent History** - All agent runs saved to Supabase database
- 🗄️ **Redis Caching** - 5-minute cache reduces API calls by 90%
- 💬 **Conversation History** - Full message history with timestamps
- 📋 **Saved Scenarios** - Save and reuse pricing scenarios for quick access
- 🔄 **Real-Time Processing** - Background job system with status polling

---

## 🏗️ Tech Stack

### **Backend** 🐍
- **FastAPI** - Modern Python web framework
- **LangGraph** - Multi-agent orchestration framework
- **OpenAI API** - GPT-4.1-mini for pricing recommendations
- **Python 3.11+** - Latest features and performance

### **Frontend** ⚛️
- **Next.js 15.1** - React 19 with App Router
- **TypeScript** - Type-safe development
- **Tailwind CSS** - Utility-first styling
- **shadcn/ui** - Beautiful component library
- **Lucide Icons** - Modern icon set
- **Framer Motion** - Smooth animations

### **Database & Cache** 💾
- **Supabase** - PostgreSQL with real-time capabilities (schema: `pricing_analyst`)
- **Upstash Redis** - Serverless job queue & caching (prefix: `pricing_analyst`)

### **External APIs** 🔌
- **Stripe API** - Product and pricing data (test mode)
- **Competitor API** - External pricing scraper/mock data

### **Deployment** 🚀
- **Railway** - Automated deployment platform for API + Web services

---

### 🏠 Homepage
![Homepage](public/demo/homepage.png)
*Beautiful landing page with video background and clear value proposition*

### 📊 Dashboard
![Dashboard](public/demo/dashboard.png)
*Comprehensive SKU pricing dashboard with KPIs, filters, and analysis table*

### 🎮 Playground
![Playground](public/demo/playground.png)
*Interactive agent playground for running pricing scenarios and getting AI recommendations*

---

## 📖 User Guide

### 📊 Using the Dashboard

1. **View SKU Overview**
   - See all SKUs with current prices, AI recommendations, and competitor medians
   - KPI cards show total SKUs, average confidence, and agent runs

2. **Filter & Search**
   - Click **"Filters"** to expand filter panel
   - Search by SKU name
   - Filter by confidence range (0-100%)
   - Filter by price range
   - Filter by trends (Up ↑, Down ↓, Flat →)

3. **Use Price Simulator**
   - Adjust the price slider to test different price points
   - See projected revenue impact and customer count changes
   - View optimal price range on the price curve chart

4. **Export Analysis**
   - Click the **Export** button on any SKU card
   - Choose to export as PDF, CSV, or copy shareable link

5. **View Live Updates**
   - Toggle **"Live market feed"** for real-time updates
   - New agent runs automatically appear in the dashboard

### 🎮 Using the Playground

1. **Select a SKU**
   - Choose a product SKU from the dropdown (e.g., "Pro - Monthly ($29/mo)")

2. **Enter Pricing Scenario**
   - Describe your pricing question: *"Should I raise the price by 10%?"*
   - Or use quick examples: "What's the optimal price for this SKU?"
   - Press **Cmd/Ctrl + Enter** to run quickly

3. **Run Analysis**
   - Click **"Run LangGraph Agent"**
   - Watch the LangGraph pipeline execute:
     - **Fetch Node** → Stripe + Competitors
     - **Compare Node** → Metrics & Analysis
     - **Suggest Node** → AI Recommendation

4. **View Results**
   - See recommended price with confidence score
   - Read AI summary explanation
   - View conversation history with message bubbles
   - Save scenario for future use

5. **Review History**
   - Click **"History"** button to view past analyses
   - Select any analysis to reload it into the playground
   - Clear history when needed

---

## 🎨 Customization

### Theme Options
- 🌙 **Dark Mode** - Default theme (easy on the eyes)
- ☀️ **Light Mode** - Clean, bright interface (toggle available)

### Dashboard Features
- **KPI Cards** - Customizable metrics display
- **Price Simulator** - Interactive revenue projection tool
- **Export Formats** - PDF, CSV, or shareable links

### Playground Features
- **Quick Examples** - Pre-configured scenario suggestions
- **Contextual Suggestions** - AI-powered prompt suggestions based on conversation
- **Saved Scenarios** - Save and reuse favorite pricing scenarios

---


---

## 🎯 LangGraph Architecture

```
POST /agent/run
    ↓
run_pricing_graph()
    ↓
┌─────────────────┐
│  Fetch Node     │  → Stripe API + Competitor API (with Redis cache)
└─────────────────┘
    ↓
┌─────────────────┐
│  Compare Node   │  → Calculate metrics (median, position, bands)
└─────────────────┘
    ↓
┌─────────────────┐
│  Suggest Node   │  → OpenAI GPT-4.1-mini (AI recommendation)
└─────────────────┘
    ↓
Result → Redis Cache → Supabase DB → API Response
```

---

## 👨‍💻 Creator

**Created by Derril Filemon**

---

## 🙏 Acknowledgments

- **LangGraph** - For multi-agent orchestration framework
- **OpenAI** - For GPT-4.1-mini API
- **Stripe** - For payment and pricing infrastructure
- **Supabase** - For database and authentication
- **Upstash** - For Redis caching
- **Railway** - For deployment platform
- **shadcn/ui** - For beautiful components
- **Next.js** - For React framework
- **FastAPI** - For Python web framework

---


<div align="center">

**⭐ Star this repo if you find it useful!**

Made with ❤️ and ☕ by [Derril Filemon](https://github.com/derril-tech)

</div>
