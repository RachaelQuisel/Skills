# Data Processing Research

## Research Checklist

1. **Understand the data format** - CSV, JSON, PDF, Excel
2. **Identify transformation needs** - Cleaning, merging, parsing
3. **Check for existing tools** - Libraries, scripts, no-code options
4. **Consider edge cases** - Multi-line values, encoding, malformed data

## Common Data Tasks

### CSV Operations
- Merging: Left join vs full merge
- Deduplication: Fuzzy matching for typos
- Cleaning: Phone normalization, email validation
- Field mapping between systems

### PDF Parsing
- Text extraction: pdfplumber, PyPDF2
- Table extraction: camelot, tabula
- Multi-page handling
- Footer/header removal

### Data Cleaning Patterns
- Phone: Remove formatting, normalize to digits
- Email: Lowercase, trim whitespace
- Names: Title case, handle suffixes
- Dates: Parse to ISO format

## Subagent Prompts

```
"Python [task] library comparison 2025"
"[Format] parsing best practices"
"[Tool] data transformation examples"
```

## Output Template

```
## Data Analysis
- Input format:
- Records count:
- Key fields:

## Transformation Plan
1. [Step] - [Tool/method]
2. [Step] - [Tool/method]

## Edge Cases
- [Case]: [Handling approach]

## Code/Script
[Working implementation]
```
