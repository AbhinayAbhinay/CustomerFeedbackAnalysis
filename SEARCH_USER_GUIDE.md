# 🎓 Search Feature User Guide

## Quick Start: How to Use Search

### Step 1: Load Some Data
1. Visit your deployed Worker URL
2. Click "Initialize Database"
3. Click "Load Mock Data"
4. You should see 8 feedback items appear

### Step 2: Try Basic Search

**Example 1: Find Security Issues**
```
Type in search box: security
Click: 🔍 Search
```
**Result:** Shows all feedback containing "security" in subject or message

**Example 2: Find Enterprise Customer Feedback**
```
Type: enterprise customer issues
Click: 🔍 Search
```
**Result:** Shows feedback from Enterprise tier customers

**Example 3: Find Critical Alerts**
```
Type: critical alerts
Click: 🔍 Search
```
**Result:** Shows only CRITICAL priority items

### Step 3: Try AI Analysis

**Example 1: Analyze Security Concerns**
```
Type: analyze security concerns
Click: 🤖 AI Analyze
```
**Result:** 
- Summary of security-related feedback
- Key insights about security issues
- Recommended actions
- Severity assessment
- Statistics (count, urgency scores, etc.)

**Example 2: Understand Enterprise Impact**
```
Type: what problems are enterprise customers facing?
Click: 🤖 AI Analyze
```
**Result:**
- Analysis of enterprise customer feedback
- Patterns and trends
- Suggested PM actions
- Priority assessment

## Search Query Cheat Sheet

### By Priority Level
| Query | What It Finds |
|-------|---------------|
| `critical` | CRITICAL alerts only |
| `high priority` | HIGH priority items |
| `urgent` | CRITICAL + HIGH combined |
| `low priority` | LOW priority items |

### By Customer Tier
| Query | What It Finds |
|-------|---------------|
| `enterprise` | Enterprise customers |
| `business` | Business tier customers |
| `free tier` | Free tier users |

### By Source
| Query | What It Finds |
|-------|---------------|
| `github` | GitHub issues |
| `discord` | Discord feedback |
| `support` or `ticket` | Support tickets |
| `email` | Email feedback |

### By Issue Type
| Query | What It Finds |
|-------|---------------|
| `security` | Security-related issues |
| `outage` or `down` | Service outages |
| `performance` or `slow` | Performance problems |
| `bug` | Bug reports |
| `api` | API-related issues |
| `database` | Database issues |

### Combined Queries
| Query | What It Finds |
|-------|---------------|
| `critical security issues` | Critical + security keywords |
| `enterprise outages` | Enterprise customers + outage keywords |
| `github bugs about api` | GitHub + bug + API keywords |
| `urgent performance problems` | High priority + performance |

## Analysis Query Examples

### Understanding Impact
```
"what are the most urgent issues?"
"analyze feedback from enterprise customers"
"summarize critical alerts"
```

### Pattern Detection
```
"analyze security concerns"
"what are the main problems?"
"identify trends in feedback"
```

### Action Planning
```
"what should I focus on today?"
"which issues need immediate attention?"
"analyze recent outages"
```

## Understanding Search Results

### Search Information Bar
After searching, you'll see:
```
Search: Searching for security-related feedback from Enterprise customers | Found: 3 results
```

This shows:
- **How AI interpreted your query** - Confirms the search understood you correctly
- **Number of results** - How many feedback items matched

### Analysis Panel
After AI analysis, you'll see:

**Summary Section** (Green box)
- 2-3 sentence overview of findings

**Severity Badge**
- Critical (red) / High (orange) / Medium (yellow) / Low (green)

**Key Insights**
- Bullet points of important patterns discovered

**Recommended Actions**
- Suggested next steps for PMs

**Statistics**
- Total items analyzed
- Breakdown by alert level
- Average urgency and sentiment scores

## Tips

### 1. Be Specific
❌ "problems"
✅ "api performance problems from enterprise customers"

### 2. Use Natural Language
You can type like you're asking a colleague:
- "show me security issues"
- "what's going on with github feedback?"
- "find critical alerts from yesterday"

### 3. Combine Filters
- "critical AND enterprise"
- "github bugs about deployment"
- "security issues OR outages"

### 4. Try Different Phrasings
If you don't get results, rephrase:
- "security" vs "vulnerabilities" vs "breach"
- "outage" vs "down" vs "not working"
- "slow" vs "performance" vs "latency"

### 5. Clear and Start Over
Click "✕ Clear" to:
- Reset search
- Close analysis panel
- Show all feedback again

## Common Workflows

### Morning Triage Workflow
1. Type: `critical alerts`
2. Click: Search
3. Review CRITICAL items first
4. Type: `analyze critical alerts`
5. Click: AI Analyze
6. Read recommended actions
7. Address highest priority items

### Customer Support Workflow
1. Type: `enterprise customer complaints`
2. Click: Search
3. Review enterprise feedback
4. Type: `analyze enterprise feedback`
5. Click: AI Analyze
6. Identify patterns affecting high-value customers

### Security Review Workflow
1. Type: `security vulnerabilities`
2. Click: Search
3. Review all security-related items
4. Type: `analyze security concerns`
5. Click: AI Analyze
6. Escalate based on severity assessment

### Weekly Review Workflow
1. Type: `analyze all feedback`
2. Click: AI Analyze
3. Review overall trends
4. Note: key insights and patterns
5. Plan: actions for next week

## Troubleshooting

### "No results found"
**Try:**
- Broader keywords: "api" instead of "api version 2.1"
- Different spelling: "outage" vs "downtime"
- Remove filters: search "security" alone first
- Check if data is loaded (click "Load Mock Data")

### Search seems slow
**Reasons:**
- Workers AI is processing your query (normal, ~1 sec)
- First query after idle may take longer
- Rate limiting if many rapid searches

**Solutions:**
- Wait a moment, it should complete
- Try keyword search (faster than AI)
- Use filter buttons for simple queries

### Analysis not showing insights
**Reasons:**
- Not enough matching feedback to analyze
- AI response parsing issue
- No results found for query

**Solutions:**
- Try a broader query
- Check if search found results first
- Use basic stats shown in analysis panel

### Query not understood correctly
**Check interpretation:**
- Look at the "Search:" bar after searching
- See how AI interpreted your query
- Rephrase if interpretation is wrong

**Example:**
```
Query: "find bugs"
Interpretation: "Searching for bug reports"  ✓ Correct

Query: "the api issues"
Interpretation: "Searching: the api issues"  Too literal, try "api issues" instead
```

## Advanced Features

### Combining with Filters
1. Use search to narrow down
2. Then click filter buttons (Critical, High, etc.)
3. Further refine results

### Export Strategy (Manual)
1. Search for what you need
2. Copy relevant feedback items
3. Use for reports, presentations, etc.

### Pattern Tracking
1. Search same query weekly
2. Compare number of results over time
3. Track if issues are increasing/decreasing

---

## Quick Reference Card

```
┌─────────────────────────────────────────────┐
│           SEARCH COMMANDS                   │
├─────────────────────────────────────────────┤
│ Find specific items:                        │
│   • Type keywords → Click Search        │
│                                             │
│ Get AI insights:                            │
│   • Type question → Click AI Analyze    │
│                                             │
│ Clear everything:                           │
│   • Click ✕ Clear                          │
│                                             │
│ Quick examples:                             │
│   • "critical security"                     │
│   • "enterprise outages"                    │
│   • "analyze github feedback"               │
└─────────────────────────────────────────────┘
```

Happy searching!
