# 🔍 Natural Language Search & Analysis Feature

## Overview

The High-Alert Feedback Triage System now includes **AI-powered natural language search** that lets Product Managers type keywords or questions to find and analyze feedback data instantly.

## Features

### 1. Keyword Search
Type natural language queries to find relevant feedback:

**Example Queries:**
- `security issues`
- `enterprise customer complaints`
- `all outages from last week`
- `github bugs`
- `critical alerts`
- `performance problems`
- `deployment issues from discord`

### 2. AI Analysis
Get intelligent insights from your feedback data:

**What It Does:**
- Summarizes matching feedback
- Identifies key patterns and trends
- Provides recommended actions
- Assesses severity (Critical/High/Medium/Low)
- Shows statistics (counts, averages, breakdowns)

## How It Works

### Search Flow
```
User types query: "security issues from enterprise customers"
         ↓
Workers AI interprets query
         ↓
Generates SQL filter: alert_level = 'CRITICAL' AND customer_tier = 'Enterprise'
         ↓
Adds keyword matching: WHERE message LIKE '%security%'
         ↓
Returns filtered results with explanation
```

### Analysis Flow
```
User types query: "what are the main security concerns?"
         ↓
System searches for relevant feedback (top 10)
         ↓
Workers AI analyzes patterns across feedback
         ↓
Returns: summary, insights, actions, severity, stats
         ↓
Displays analysis panel with recommendations
```

## Using the Search Interface

### Basic Search

1. **Type your query** in the search box:
   ```
   "show me all critical alerts"
   ```

2. **Click 🔍 Search** or press Enter

3. **View results** filtered to your query

4. **See interpretation** showing how the system understood your query

### AI Analysis

1. **Type your question** in the search box:
   ```
   "analyze security feedback from enterprise customers"
   ```

2. **Click 🤖 AI Analyze**

3. **View analysis panel** with:
   - Summary of findings
   - Key insights
   - Recommended actions
   - Severity assessment
   - Statistics and metrics

4. **Review matching feedback** shown below the analysis

### Clearing Results

Click **✕ Clear** to:
- Reset search box
- Remove analysis panel
- Show all feedback again

## Query Examples

### By Alert Level
- `critical alerts`
- `high priority items`
- `urgent feedback`
- `low priority questions`

### By Customer Tier
- `enterprise customer issues`
- `business tier feedback`
- `free tier requests`

### By Source
- `github issues`
- `discord complaints`
- `support tickets`
- `email feedback`

### By Issue Type
- `security vulnerabilities`
- `api outages`
- `performance problems`
- `database errors`
- `deployment failures`

### By Combination
- `critical security issues from enterprise customers`
- `github bugs about performance`
- `all outages from support tickets`
- `urgent api problems`

### Analysis Questions
- `what are the main issues affecting enterprise customers?`
- `analyze recent security concerns`
- `summarize critical alerts`
- `what feedback needs immediate attention?`

## Technical Implementation

### API Endpoints

**POST /api/search**
```json
{
  "query": "security issues from enterprise"
}
```

**Response:**
```json
{
  "success": true,
  "query": "security issues from enterprise",
  "interpretation": "Searching for security-related feedback from Enterprise customers",
  "results": [...],
  "count": 5
}
```

**POST /api/analyze**
```json
{
  "query": "analyze critical alerts"
}
```

**Response:**
```json
{
  "success": true,
  "query": "analyze critical alerts",
  "summary": "Found 3 critical issues requiring immediate attention...",
  "insights": [
    "Multiple security vulnerabilities reported",
    "Enterprise customers are heavily impacted"
  ],
  "recommended_actions": [
    "Escalate security issues to engineering",
    "Contact affected enterprise customers"
  ],
  "severity_assessment": "critical",
  "stats": {
    "total": 3,
    "by_alert": { "critical": 3, "high": 0 },
    "avg_urgency": 0.95
  },
  "matching_feedback": [...]
}
```

### AI Integration

**Query Parsing:**
- Model: `@cf/meta/llama-3.1-8b-instruct`
- Converts natural language to SQL WHERE clauses
- Extracts relevant keywords
- Provides human-readable interpretation

**Feedback Analysis:**
- Model: `@cf/meta/llama-3.1-8b-instruct`
- Analyzes up to 10 matching feedback items
- Generates insights and recommendations
- Assesses severity and impact

### Fallback System

If Workers AI is unavailable or fails:
- **Search**: Falls back to keyword-based SQL LIKE queries
- **Analysis**: Generates basic statistical analysis from data
- System remains functional even without AI

## Smart Query Understanding

The AI understands:

### Alert Levels
- "critical" → `alert_level = 'CRITICAL'`
- "urgent" or "high priority" → `alert_level IN ('CRITICAL', 'HIGH')`
- "low priority" → `alert_level = 'LOW'`

### Customer Tiers
- "enterprise" → `customer_tier = 'Enterprise'`
- "business" → `customer_tier = 'Business'`

### Sources
- "github" → `source LIKE '%GitHub%'`
- "discord" → `source LIKE '%Discord%'`
- "support" or "ticket" → `source LIKE '%Support%'`

### Issue Keywords
- Extracts: security, outage, performance, bug, api, database, deployment
- Applies as: `message LIKE '%keyword%' OR subject LIKE '%keyword%'`

## Use Cases for PMs

### 1. Daily Triage
**Query:** `critical alerts from yesterday`
**Result:** Focus on most urgent items first

### 2. Customer Segmentation
**Query:** `enterprise customer feedback`
**Result:** Prioritize high-value customers

### 3. Issue Pattern Detection
**Query:** `analyze security concerns`
**Result:** Identify recurring security themes

### 4. Source Monitoring
**Query:** `github issues about api`
**Result:** Track developer-reported problems

### 5. Severity Assessment
**Query:** `analyze feedback from last week`
**Result:** Understand overall feedback health

### 6. Quick Lookups
**Query:** `outages`
**Result:** Instant view of service issues

## Performance

- **Search Query**: ~500ms (including AI interpretation)
- **Analysis**: ~1-2 seconds (AI processing + data aggregation)
- **Fallback Search**: ~100ms (pure SQL, no AI)

## Best Practices

### Writing Effective Queries

✅ **Good Queries:**
- `critical security issues` (specific, actionable)
- `enterprise customer complaints about performance` (detailed)
- `github bugs` (clear source + type)

❌ **Less Effective:**
- `stuff` (too vague)
- `problems issues bugs` (redundant keywords)
- `the` (stop words)

### When to Use Search vs Analysis

**Use Search when:**
- You know what you're looking for
- You want to filter to specific criteria
- You need quick results

**Use Analysis when:**
- You want to understand patterns
- You need recommendations
- You're exploring the data
- You want statistical insights

## Future Enhancements

Potential improvements:
1. **Date range filters**: "feedback from last 7 days"
2. **Sentiment analysis**: "show me angry customers"
3. **Trend detection**: "compare this week vs last week"
4. **Auto-suggestions**: Query autocomplete
5. **Saved searches**: Store frequent queries
6. **Export results**: Download filtered data

## Troubleshooting

### "No results found"
- Try broader keywords
- Check spelling
- Use different phrasing
- Try searching without filters first

### "Analysis taking too long"
- Workers AI might be rate limited
- System will fall back to basic analysis
- Try again in a few moments

### "Search not understanding my query"
- Use simpler language
- Try specific keywords (security, outage, critical)
- Use filter buttons for basic filtering

---

This natural language interface makes feedback triage **10x faster** by eliminating the need for complex filters and manual data exploration. Just type what you're looking for and let AI do the work!
