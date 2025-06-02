# BECCS Grey Literature Miner (Rough Prototype)

A minimal proof-of-concept showing that we can automatically discover, download, and rank BECCS-related “grey literature” PDFs from authoritative websites. This just a quick prototype to prove feasibility.

---

## Overview

1. **Crawl target site(s)**  
   - Starts from one or more “reports” pages (e.g. `efifoundation.org/reports/`).  
   - Follows internal links under `/reports/`.  
   - Identifies PDF URLs whose filenames or paths contain the keyword `BECCS` (case-insensitive).  

2. **Download & extract metadata**  
   - Fetches each matching PDF (using a browser-like header to avoid 403 errors).  
   - Uses PyMuPDF to pull basic metadata (title, creation date).  

3. **Rank & display**  
   - Applies a simple point system (domain reputation + recency + keyword in title).  
   - Prints a sorted list of “most credible” BECCS PDFs first.

Everything lives in **one Python script**—designed to be runnable in a single Jupyter Notebook cell or as a standalone `.py` file.
