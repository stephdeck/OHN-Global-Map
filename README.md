# Business History Academics Map - Opt-In Version

This version displays individual details for academics who have opted in by filling out the "Interests" field in the directory spreadsheet.

## What's Different from the Regular Version

### Regular Version (`index.html` + `academics_data.json`)
- Shows **only aggregate counts** by location
- Privacy-focused: NO individual names, affiliations, or details visible
- All 432 academics represented as numbers only

### Opt-In Version (`index_with_optin.html` + `academics_data_with_optin.json`)
- Shows **individual details** for academics who opted in (6 people)
- Shows **aggregate counts** for academics who did not opt in (426 people)
- When you click on an opted-in individual's marker, you see:
  - Full name
  - University affiliation
  - Research interests
  - Location

## Data Summary

**Total:** 432 business historians

**Breakdown:**
- **4 opted-in** (individual markers with full details)
- **428 not opted-in** (aggregate markers showing counts only)
- **78 total markers** (4 individuals + 33 city aggregates + 41 country aggregates)

## Opted-In Academics

These 4 academics have their details visible on the map:

1. **Stephanie Decker** - FAcSS, FBAM, University of Birmingham (UK)
   - Research Interests: historical methods in management, multinationals, Africa, Ghana, Nigeria, archival research, digital sources
   - Location: Birmingham, UK

2. **Christina Lubinski** - Professor of Business History, Copenhagen Business School
   - Research Interests: Historical entrepreneurship, historical methods, India, rhetorical history
   - Location: Copenhagen, Denmark

3. **Adam Nix** - University of Birmingham
   - Research Interests: digital sources, organizational corruption, historical methods, responsible business
   - Location: Birmingham, UK

4. **Nicholas D Wong** - Senior Lecturer in Entrepreneurship, Newcastle Business School, Northumbria University
   - Research Interests: family business, historical entrepreneurship
   - Location: Newcastle, UK

## How Opt-In Works

Academics opt in by:
1. Setting the **"Opt-in?"** column to **"yes"** (or "y") in the BH_AcademicDirectory spreadsheet
2. Their information then appears as an individual marker on the map
3. Clicking their marker shows their name, affiliation, and research interests

## Files

- `index_with_optin.html` (13 KB) - Complete website with opt-in display logic
- `academics_data_with_optin.json` (10 KB) - Data file with individual markers for opted-in academics

## Deployment

Deploy exactly like the regular version:

### Quick Deploy to GitHub Pages

1. Create a new repository or use a separate folder in your existing repository
2. Upload both files:
   - `index_with_optin.html` (rename to `index.html` in the repository)
   - `academics_data_with_optin.json`
3. Enable GitHub Pages
4. Access at: `https://yourusername.github.io/repository-name/`

**Important:** If you want to deploy this as your main map, rename:
- `index_with_optin.html` → `index.html`
- Then upload both files

## Privacy Considerations

**Opted-In Academics:**
- These individuals have explicitly chosen to make their information public
- Their details are visible to anyone viewing the map
- Information shown: Name, affiliation, research interests, location

**Not Opted-In Academics:**
- Remain anonymous in aggregate counts
- No individual details visible
- Privacy fully protected

## How Individual Markers Work

**Visual Differences:**
- Individual markers have the same size/color scheme as aggregate markers (both show "1")
- However, clicking reveals different information:
  - **Individual marker:** Shows name, affiliation, interests
  - **Aggregate marker:** Shows "1 business historian"

**Location Precision:**
- Individual markers have a small random offset (±200 meters) to prevent exact overlap with city markers
- This means multiple individuals in the same city won't stack directly on top of each other

## Updating the Map

When academics opt in (or opt out):

1. **Update the Excel file** (add/remove data in "Interests" column)
2. **Regenerate the JSON file** using the Python script
3. **Re-upload** `academics_data_with_optin.json` to GitHub
4. Changes go live in 2-3 minutes

**Note:** You'll need to regenerate the JSON file whenever:
- Someone opts in (fills "Interests" column)
- Someone opts out (removes "Interests" data)
- Any data changes (name, affiliation, interests, location)

## Comparison with Regular Version

| Feature | Regular Version | Opt-In Version |
|---------|----------------|----------------|
| Total academics shown | 432 | 432 |
| Individual names visible | ❌ No | ✅ Yes (4 opted-in) |
| Affiliations visible | ❌ No | ✅ Yes (4 opted-in) |
| Research interests visible | ❌ No | ✅ Yes (4 opted-in) |
| Privacy-focused | ✅ Yes (100%) | ⚠️ Partial (428/432) |
| Total markers | 139 | 78 |
| File size | 16 KB | 10 KB |

## Which Version to Use?

**Use Regular Version if:**
- Privacy is the top priority
- You want complete anonymity for all academics
- You only need aggregate statistics
- You're making a public-facing research map

**Use Opt-In Version if:**
- You want to showcase individual academics who consent
- You want to highlight research interests
- You want a mix of privacy and visibility
- You're building a networking/discovery tool

## Technical Notes

**Marker Types in JSON:**
- `type: "individual"` - Opted-in academic (has name, affiliation, interests fields)
- `type: "city"` - City aggregate (count only, excludes opted-in individuals)
- `type: "country"` - Country aggregate (count includes everyone, opted-in + not opted-in)

**Counting Logic:**
- Individual markers count as 1 person each
- City aggregates count non-opted-in people in that city
- Country aggregates count all people in that country (opted-in + not opted-in)
- **Total displayed: 432** (sum of country markers)

**Example - Newcastle, UK:**
- 5 individual markers (opted-in academics)
- 1 city aggregate marker showing "12" (non-opted-in academics)
- Total Newcastle: 5 + 12 = 17
- UK country marker includes all 17

## Questions?

For more information on:
- **Deployment:** See main DEPLOY_NOW.md
- **Data updates:** See UPDATE_INSTRUCTIONS.md  
- **Privacy policy:** See PRIVACY_DESIGN.md
- **Opt-in form:** See FORM_SETUP.md

---

**Version:** Opt-In Display Version  
**Last Updated:** January 2026  
**Opted-In Academics:** 4 / 432 (0.9%)
