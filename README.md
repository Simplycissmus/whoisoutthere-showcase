# WhoisOutThere - See the People Behind Every Job

[![Live Demo](https://img.shields.io/badge/Live-Production-success)](https://whoisoutthere.com)
[![Architecture](https://img.shields.io/badge/Architecture-8%20Microservices-blue)]()
[![i18n](https://img.shields.io/badge/i18n-DE%20%7C%20EN%20%7C%20FR-green)]()
[![Portfolio](https://img.shields.io/badge/Developer-aeberhard.ai-red)](https://aeberhard.ai)

## 🧠 The Problem: Companies Only See What They Filter For

After working in government digital transformation and observing recruitment patterns, I noticed companies filter out qualified people with 8 years experience because their job posting demanded 10.

**Reality check:** Minor requirement differences exclude major talent pools.

The journey through various sectors - from statistics to digital transformation - revealed a consistent pattern:

**The insight:** The talent shortage is often a visibility problem.

## Human-Centric Talent Discovery

WhoisOutThere transforms job postings into concrete human insights. Instead of talking about requirements and market conditions, the platform shows **WHO** actually applies and **WHO** gets excluded by your current posting.

The core philosophy: Every job posting reaches specific types of people and excludes others. By understanding these patterns, companies can make small changes that dramatically expand their talent pool.

## What It Actually Delivers

WhoisOutThere is a talent intelligence platform that transforms job postings into strategic recruitment insights:

### **Input**: Any job posting (PDF or text)
### **Output**: Premium Analysis Dashboards

**Currently Available in Production:**
- **Job Overview**: Basic analysis of requirements and company culture
- **Market Insights**: Workforce demographics and statistics
- **Premium Dashboards**: Talent segments, exclusion analysis, inclusion opportunities

**Roadmap Features:**
- Concrete persona profiles with demographics
- Quantified exclusion impact analysis
- ROI calculations for requirement adjustments
- Skills transferability insights

### **Technical Foundation**
- **Phase 1 Analysis**: 18 AI modules extract job requirements, company culture, psychological profile, ISCO/NACE classifications, and context intelligence
- **Phase 2 Synthesis**: 3-stage pipeline generates talent segments using labor market intelligence and demographic modeling
- **Data Normalization**: Chart-ready APIs transform AI analysis into visualization-friendly statistical data

## Railway Microservices Architecture

**Performance breakthrough**: Moved from Supabase Edge Functions (2-minute timeout) to Railway microservices (unlimited processing time).

### The 8-Service Pipeline

1. **Frontend Service** - Next.js 15.3.2 with credit-based payment system and trilingual UI
2. **Inngest Orchestrator** - Coordinates async workflows between services
3. **PDF Extraction** - Multi-strategy processing: PyMuPDF (fast) → Tesseract OCR (images) → AI Vision (fallback)
4. **Analysis Engine** - 18 parallel AI modules extract job requirements, culture, psychology, and market context
5. **Phase 2 Synthesis** - 3-stage pipeline generates talent segments with Swiss labor market intelligence
6. **Data Normalization** - Transforms AI analysis into statistical APIs for dashboards
7. **Context Discovery** - Swiss workforce demographics and market intelligence engine
8. **Reports Generator** - Professional PDF reports with talent visualization (in development)

### Tech Stack Excellence

- **Frontend**: Next.js 15.3.2, TypeScript, TailwindCSS with Design System V2.1
- **Database**: PostgreSQL 17.4 with 17 optimized JSONB GIN indexes (50-80% query performance improvement)
- **AI Architecture**: Provider Factory pattern with intelligent orchestration
  - Multi-provider support (OpenAI, Google AI, Anthropic)
  - Automatic failover when models are unavailable
  - Cost-optimized model selection per task type
- **Infrastructure**: Railway auto-scaling with zero downtime deployments
- **Security**: Row-Level Security on all 31 tables with 50+ policies
- **Payments**: Stripe integration with credit-based system (€49/€99/€199) to cover infrastructure costs

## Real Performance Numbers (Honest Production Data)

| Component | Current Performance | Notes |
|-----------|-------------------|--------|
| **PDF Extraction** | ~0.2s (PyMuPDF) | Works reliably for text PDFs |
| **Phase 1 Analysis** | ~90 seconds | 18 parallel AI modules |
| **Phase 2 Synthesis** | 5-6 minutes | Persona generation via Railway |
| **Total Pipeline** | ~8 minutes | End-to-end processing |
| **API Response** | 200-500ms | Database queries optimized |
| **Completion Rate** | ~85% | Some timeout issues remain |

**What Actually Works:**
- Basic job requirement extraction
- Swiss workforce statistics integration
- AI-generated persona concepts (quality varies)
- Multi-language support (DE/EN/FR)

## Global Reach with Local Intelligence

Built with international capabilities:

- **Statistical Integration**: Real government and market data
- **ISCO-08/NACE**: International job classification standards
- **Multilingual Support**: German, English, French interfaces
- **Regional Awareness**: Local market differences considered
- **Cultural Context**: Understanding of regional work cultures

**Note**: Currently optimized for DACH region with global expansion underway.

## Engineering Challenges Solved

**1. Database Performance Crisis**
- **Problem**: Complex JSONB queries taking 10+ seconds on large datasets
- **Solution**: 17 specialized JSONB GIN indexes designed for our query patterns
- **Result**: 50-80% query performance improvement, <200ms API responses

**2. AI Service Reliability**
- **Problem**: Gemini rate limits causing analysis failures
- **Solution**: Multi-provider fallback chain with graceful degradation
- **Result**: 95%+ success rate despite model availability issues

**3. Processing Time Constraints**
- **Problem**: Supabase Edge Functions 2-minute timeout killed complex analysis
- **Solution**: Migration to Railway microservices with unlimited execution time
- **Result**: 18-module analysis pipeline running without timeouts

**4. Multilingual Consistency**
- **Problem**: Maintaining German/English/French consistency across 8 services
- **Solution**: Zero hardcoded strings policy with CI/CD validation
- **Result**: Professional trilingual experience throughout platform

## The Story Behind This

### Why I Built This

Working in digital transformation and statistics, I kept seeing the same pattern: job postings that accidentally exclude qualified people over minor differences. A developer with 8 years experience filtered out because the posting said 10.

### The Approach

Instead of another matching algorithm, I built something that shows companies the human impact of their requirements. Not abstractions or percentages - actual personas with names, backgrounds, and life situations.

## 💭 What I Learned (Technical & Personal)

### Technical Learnings
- **PostgreSQL optimization matters**: JSONB indexes made queries 5x faster
- **Railway beats Edge Functions**: No more 2-minute timeout constraints
- **AI fallbacks are essential**: Multiple providers prevent single points of failure
- **i18n is harder than expected**: Maintaining 3 languages across 8 services

### Personal Insights
- **Real problem validation**: Companies genuinely struggle to see who they exclude
- **Complexity vs usability**: Simpler UI often better than showing all data
- **Swiss market first**: Better to excel in one market than be mediocre globally
- **Building alone is hard**: But it ensures consistent vision

## Production Status (Live Since September 16, 2025)

**What's Working:**
- Live platform processing job postings daily
- Robust PDF import and text extraction
- AI analysis of job requirements
- Statistical data integration
- Multi-language interface (DE/EN/FR)

**Current Limitations:**
- 8-minute processing time (optimizing for speed)
- Persona quality varies (improving with more data)
- PDF report generation not yet fully optimized
- Some API timeout issues under heavy load

**What Makes It Unique:**
- Focus on WHO gets excluded, not just who qualifies
- Real Swiss federal statistics integration
- Concrete personas instead of abstract segments
- Built by someone who understands both tech and government

**🔧 Engineering Roadmap:**
- **Visualization Enhancement**: Better dashboards and data presentation
- **Report Automation**: Professional PDF generation with talent insights
- **Platform Robustness**: Improve reliability and error handling
- **User Feedback Integration**: Continuous improvement based on real usage
- **Global Expansion**: Extend proven approach to more markets

## 🔗 Connect & Try It

**Live Platform**: [whoisoutthere.com](https://whoisoutthere.com)
**GitHub**: [@Simplycissmus](https://github.com/Simplycissmus)
**LinkedIn**: [Patric Aeberhard](https://www.linkedin.com/in/patricaeberhard/)
**Portfolio**: [aeberhard.ai](https://aeberhard.ai)

---

*Built with the conviction that every person's potential deserves to be seen, not filtered out by arbitrary requirements.*