# Research Paper Summarization Script

## Overview
This Python script summarizes PDF research papers using Qwen - Plus or Qwen - Turbo models. It reads PDF text, gets summaries from the models, and exports results to Excel.

## Key Differences from Qwen - Long
- **Input Limits**: Qwen - Plus has a 98304 - token limit, Qwen - Turbo 1M tokens. If input exceeds Qwen - Plus limit, it switches to Qwen - Turbo.
- **Model Selection**: Offers choice between Qwen - Plus and Qwen - Turbo, unlike Qwen - Long - focused previous script.
- **Text Reading**: Uses `langchain` to read and split PDF text locally before API call.

## Features
- Find PDFs in a folder and read their content.
- Summarize text with Qwen models, switch models if needed.
- Parse summaries into sections, clean text, format dates.
- Export data to Excel and save raw summaries as TXT.

## Requirements
- Python 3.x
- Libraries: `os`, `datetime`, `typing`, `pandas`, `re`, `langchain_community`, `openai`, `openpyxl`
- Valid Qwen API key

## Installation
```bash
pip install pandas langchain_community openai openpyxl
```

## Configuration
Update `CONFIG` in `main` with API key, PDF folder, output file, and prompt file paths.

## Usage
1. Put PDFs in the specified folder.
2. Create a user prompt file.
3. Run the script:
```bash
python script_name.py
```
4. Results are saved as TXT and timestamped Excel file.

## Classes
### PDFProcessor
- `process_folder`: List PDF paths in a folder.
- `read_pdf`: Read and split PDF text.

### QwenAPI
- `__init__`: Initialize API client.
- `get_summary`: Summarize text with chosen model.

### ResultExporter
- `to_excel`: Export results to Excel.
- `parse_sections`: Parse summary into sections.
- `clean_text`: Clean text.
- `format_date`: Format date strings. 
