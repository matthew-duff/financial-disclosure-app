## Unbezzle
AI-powered financial disclosure analysis for family lawyers

### Recognition
Unbezzle won first place in the #TransformLaw KWM Prize, hosted by UQ Law School and King & Wood Mallesons. See announcement: [Algorithmic financial analysis platform for family lawyers awarded first place](https://law.uq.edu.au/article/2024/03/algorithmic-financial-analysis-platform-family-lawyers-awarded-first-place).

### What it does
Unbezzle ingests bank statements (CSV), uses AI to extract structured transaction metadata (category, merchant, location where possible), and performs analysis to surface the items that matter in family law disclosure.

- **Standout detection**: Flags transactions that are outliers relative to category, merchant, or the statement overall
- **Merchant grouping**: Aggregates and filters by merchant to accelerate review
- **Trend analysis**: Shows income and expense distributions and trends over time
- **Pre/post-separation views**: Compare spending patterns before and after separation
- **Collaborative interface**: Client and solicitor interfaces for discussing flagged transactions

### Impact (from pitch deck)
- **Time saved per week**: 4.5 hours
- **Time spent on disclosure per year**: 260 hours
- **Average family lawyer salary**: $115,000
- **Annual cost of disclosure per lawyer**: ~$13,618
- **Case study (Whippet Legal)**: Reduced weekly workload by 4.5 hours, nearly $15k annual savings per family lawyer

### Market sizing (AU)
- **Total family lawyers**: 7,720
- **Lawyers using software solutions**: 59%
- **TAM (annual spend on disclosure)**: ~$105.13M
- **SAM**: ~$62M
- **Assumed willingness to pay / value**: 10%
- **SOM**: ~$6.01M

### Pricing (SaaS)
- **Solo Practice**: $125/month
  - 100 credits/month
  - Multiple accounts
  - White-labelling
  - Priority queuing
- **Firm**: $298/month
  - 250 credits/month
  - Multiple accounts (3)
  - White-labelling
  - Priority queuing
- **Firm Plus**: $745/month
  - 1250 credits/month
  - Multiple accounts (10)
  - White-labelling
  - Priority queuing

Credit purchase rate:
- Solo/Firm: $1 per credit
- Firm Plus: $0.5 per credit

### Security, privacy, and compliance
- **Data sovereignty**: MongoDB and DigitalOcean databases hosted on Australian servers
- **Encryption**: SSL enforced for all connections; data stored in encrypted databases
- **Account security**: Login required; password reset security protocol implemented; 2FA planned

### Risks and mitigations
- **Existing competitors adding similar features** → Feature set is hard to box; consider patenting proprietary algorithms
- **Low barrier to entry; new competitors** → Build brand, patent core IP, maintain velocity
- **Slow initial growth** → Leverage team marketing, lead magnets, referral program, targeted outreach
- **Low user trust; new brand** → SSL, secure AU hosting, brand building through exposure and case studies

### Product architecture (at a glance)
- **Client interfaces**: Separate client and solicitor views; upload statements and review flagged items
- **AI categorisation**: Extracts merchant/category/location attributes
- **Quantitative flagging**: Outlier detection to focus review on standout transactions
- **Discussion workflow**: In-app context for questioning and resolving flagged items

### Tech stack
- **Front-end**: Svelte, Tailwind CSS
- **Back-end**: Python (Flask)
- **Databases**: MongoDB (primary), Redis (caching)

### Repository layout (key files)
- `src/` front-end (Svelte UI and components)
- `server.py` Flask API server
- `analysis.py` and `interpreter.py` analysis utilities
- `public/` static assets
- `dist/` production build

### Local development
1) Backend (Python 3.12 recommended)
```
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python server.py
```

2) Frontend (Node 18+ recommended)
```
npm install
npm run dev
```

3) Build for production
```
npm run build
```

### How it works (simplified flow)
1. Client or solicitor uploads statements (CSV)
2. Backend extracts transactions and applies AI categorisation
3. Quantitative algorithms flag standout transactions
4. UI groups by merchant, shows trends, and supports discussion workflows

### Contributing
Issues and PRs are welcome. Please ensure changes are well-scoped, linted, and tested.

### License
Copyright © Unbezzle. All rights reserved.
