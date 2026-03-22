# Python Workflows - Excel Processing

This repository contains Python workflows for analyzing and filtering Excel files using GitHub Actions automation.

## Directory Structure

```
python-_workflows/
├── data/
│   ├── input/          # Place input Excel files here
│   └── output/         # Processed Excel files output location
├── .github/
│   └── workflows/
│       └── excel-process.yml    # GitHub Actions workflow
├── excel_analyzer.py   # Excel analysis script
├── excel_filter.py     # Excel filtering script
├── requirements.txt    # Python dependencies
└── README.md           # This file
```

## Getting Started

### Input Excel Files
- Place your input Excel files in the `data/input/` directory
- The workflow will automatically process them

### Output
- Processed files will be saved to `data/output/`
- Results are also available as GitHub Actions artifacts

## Workflow Details

### Triggers
- **On Push**: Runs when code is pushed to the main branch
- **Scheduled**: Runs automatically every hour (configurable via cron schedule)

### Steps
1. Checks out the repository code
2. Sets up Python 3.10 environment
3. Installs dependencies from requirements.txt
4. Runs excel_analyzer.py
5. Runs excel_filter.py
6. Uploads output as artifacts

## Scripts

### excel_analyzer.py
Analyzes Excel files and generates reports.

### excel_filter.py
Filters and processes Excel data based on specified criteria.

## Requirements
See `requirements.txt` for Python package dependencies.

## Usage

### Local Testing
```bash
pip install -r requirements.txt
python excel_analyzer.py
python excel_filter.py
```

### Automated via GitHub Actions
Simply push changes or wait for the scheduled execution. Monitor the workflow in the Actions tab.

## Customization

### Change Workflow Schedule
Edit `.github/workflows/excel-process.yml` and modify the cron schedule:
```yaml
schedule:
  - cron: '0 * * * *'  # Change this to your desired schedule
```

### Common Cron Schedules
- `'0 * * * *'` - Every hour
- `'0 0 * * *'` - Daily at midnight
- `'0 0 * * 0'` - Weekly on Sunday
- `'*/30 * * * *'` - Every 30 minutes

## License
This project is open source and available for use.