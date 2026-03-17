# AI Content Engine

**Built by Michael Eyo using Claude Code**

AI-powered content intelligence platform that transforms keyword research into strategic, SEO-optimized content through intelligent analysis and automated generation.

🌐 **Live Demo**: [https://ai-content-engine-ecru.vercel.app](https://ai-content-engine-ecru.vercel.app)

---

## 🚀 Features

### Core Capabilities
- **AI Keyword Generation**: GPT-4o-powered keyword research with volume, difficulty, and opportunity scoring
- **SERP Intelligence**: Analyze top 10 organic results, People Also Ask, and related searches
- **Content Gap Analysis**: Identify what competitors cover and what's missing
- **Topic Clustering**: Hub-and-spoke content organization with pillar pages and supporting content
- **Automated Briefs**: Detailed content outlines with SEO optimization
- **AI Content Generation**: Brand-aware, location-optimized content with competitor mention guardrails

### Advanced Features
- **Brand Integration**: Automatically extracts and weaves brand name throughout content
- **Location Context**: GEO-optimized content with local references and examples
- **Competitor Guardrails**: Prevents mentioning competitor names or products
- **Multi-Format Support**: FAQ, how-to, listicles, comparisons, social media, video scripts, and more
- **Professional UI**: Step-by-step wizard with progress tracking and real-time feedback

---

## 🛠️ Tech Stack

- **Framework**: Next.js 14 (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS v3
- **AI**: OpenAI GPT-4o
- **APIs**: SERP API, Google Places API
- **Deployment**: Vercel
- **Version Control**: Git + GitHub

---

## 📋 Workflow

1. **Step 1: Keywords** - Enter website URL, business description, and optional seed keywords
2. **Step 2: SERP Analysis** - Select 5-10 keywords and analyze search results
3. **Step 3: Gap Analysis** - Identify content opportunities and competitive gaps
4. **Step 4: Clustering** - Generate hub-and-spoke topic clusters
5. **Step 5: Briefs** - Create detailed content outlines
6. **Step 6: Generate** - AI-powered content creation with brand and location context

---

## 🔧 Installation

### Prerequisites
- Node.js 18+
- npm or yarn
- Git

### Clone Repository
```bash
git clone https://github.com/michaelaeyo-lab/ai-content-engine-.git
cd ai-content-engine-
npm install
```

### Environment Variables

Create a `.env.local` file in the root directory:

```env
# Required
OPENAI_API_KEY=sk-proj-YOUR-OPENAI-KEY
SERP_API_KEY=YOUR-SERP-API-KEY

# Optional
GOOGLE_PLACES_API_KEY=YOUR-GOOGLE-PLACES-KEY
FIRECRAWL_API_KEY=YOUR-FIRECRAWL-KEY
PLEPER_API_KEY=YOUR-PLEPER-KEY
PLEPER_API_SIGNATURE=YOUR-PLEPER-SIGNATURE
```

#### API Keys

**OpenAI API** (Required)
- Get your API key: [platform.openai.com/api-keys](https://platform.openai.com/api-keys)
- Used for: Keyword generation, content analysis, content generation
- Pricing: ~$0.01-0.05 per content piece

**SERP API** (Required)
- Get your API key: [serpapi.com](https://serpapi.com)
- Used for: Search result analysis, competitor research
- Free tier: 100 searches/month
- Pricing: $50/month for 5,000 searches

**Google Places API** (Optional)
- Get your API key: [console.cloud.google.com](https://console.cloud.google.com)
- Used for: Local business data enrichment
- Free tier: $200/month credit

**FireCrawl API** (Optional)
- Get your API key: [firecrawl.dev](https://firecrawl.dev)
- Used for: Website crawling (currently optional)
- Free tier: 500 credits/month

---

## 🚦 Running Locally

```bash
# Development mode
npm run dev

# Build for production
npm run build

# Start production server
npm start
```

Access at: **http://localhost:3011**

---

## 📦 Deployment

### Vercel (Recommended)

1. Push code to GitHub
2. Import project on [vercel.com](https://vercel.com)
3. Add environment variables
4. Deploy!

**Current Production URL**: [https://ai-content-engine-ecru.vercel.app](https://ai-content-engine-ecru.vercel.app)

---

## 📁 Project Structure

```
ai-content-engine/
├── app/
│   ├── api/
│   │   └── content/
│   │       ├── keywords/         # Keyword generation
│   │       ├── serp/             # SERP analysis
│   │       ├── gaps/             # Gap analysis
│   │       ├── clusters/         # Topic clustering
│   │       ├── briefs/           # Brief generation
│   │       ├── generate/         # Content generation
│   │       ├── multi-format/     # Multi-format content
│   │       ├── geo-optimize/     # GEO optimization
│   │       ├── competitor-intel/ # Competitor analysis
│   │       ├── serp-features/    # SERP features analysis
│   │       ├── calendar/         # Content calendar
│   │       └── authority-map/    # Topical authority
│   ├── page.tsx                  # Main Content Engine UI
│   ├── layout.tsx                # Root layout
│   └── globals.css               # Global styles
├── public/                       # Static assets
├── package.json                  # Dependencies
├── tsconfig.json                 # TypeScript config
├── tailwind.config.js            # Tailwind config
└── next.config.js                # Next.js config
```

---

## 🎯 API Endpoints

### `/api/content/keywords`
Generates keyword suggestions with volume, difficulty, and opportunity scores.

**Input:**
```json
{
  "url": "https://example.com",
  "businessDescription": "Local HVAC company",
  "manualKeywords": ["hvac repair", "ac installation"],
  "location": "Miami, FL"
}
```

**Output:**
```json
{
  "keywords": [
    {
      "keyword": "emergency hvac repair miami",
      "volume": 2400,
      "difficulty": 45,
      "opportunity": 85
    }
  ]
}
```

### `/api/content/serp`
Analyzes SERP results for target keywords.

**Input:**
```json
{
  "keywords": ["hvac repair miami"],
  "location": "Miami, FL"
}
```

**Output:**
```json
{
  "results": [
    {
      "keyword": "hvac repair miami",
      "topResults": [...],
      "paa": ["How much does HVAC repair cost?"],
      "relatedSearches": ["24 hour hvac repair miami"]
    }
  ]
}
```

### `/api/content/gaps`
Identifies content gaps and opportunities.

**Input:**
```json
{
  "websiteUrl": "https://example.com",
  "serpResults": [...],
  "keywords": ["hvac repair miami"]
}
```

### `/api/content/clusters`
Generates topic clusters with pillar and supporting content.

### `/api/content/briefs`
Creates detailed content briefs with outlines and SEO guidance.

### `/api/content/generate`
Generates full AI-powered content with brand and location integration.

**Input:**
```json
{
  "brief": {...},
  "websiteUrl": "https://example.com",
  "location": "Miami, FL"
}
```

---

## 🎨 Content Quality Guardrails

- ✅ **Brand Integration**: Mentions brand 2-3 times naturally
- ✅ **Location Context**: Weaves location throughout content
- ❌ **No Competitor Mentions**: Never names competitor brands
- ✅ **Authoritative Tone**: Positions client as the trusted solution
- ✅ **SEO Optimized**: Keyword placement, heading structure, readability

---

## 💰 Cost Estimates

**Per Content Piece:**
- Keyword Generation: ~$0.002
- SERP Analysis: ~$0.05-0.10
- Gap Analysis: ~$0.005
- Clustering: ~$0.005
- Brief Generation: ~$0.01
- Content Generation: ~$0.01-0.02

**Total per content piece**: ~$0.08-0.15

---

## 🔒 Security

- Environment variables secured in `.env.local`
- API keys never exposed to client
- Server-side API calls only
- HTTPS enforced on Vercel

---

## 📊 Performance

- Static generation where possible
- API routes optimized for serverless
- Tailwind CSS for minimal bundle size
- Next.js 14 App Router for fast navigation

---

## 🤝 Contributing

This is a proprietary project built by Michael Eyo. Not open for public contributions.

---

## 📝 License

© 2026 Michael Eyo. All rights reserved.

---

## 🙏 Credits

- **Built by**: Michael Eyo
- **Powered by**: Claude Code (Autonomous AI Coding)
- **AI Model**: OpenAI GPT-4o
- **Framework**: Next.js 14
- **Deployment**: Vercel

---

## 📞 Support

For questions or support, contact Michael Eyo.

---

**Built with 🤖 Claude Code - The future of autonomous coding**
