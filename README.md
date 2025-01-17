Here's the complete `README.md` file content for your package:

```markdown
# linkedin-search-job

A Python package to scrape job listings from LinkedIn based on various filters.

## Installation

Install the package using pip:

```sh
pip install linkedin-search-job
```

## Usage

### From the Command Line

You can run the scraper directly from the command line:

```sh
linkedin_search_job
```

### As a Module in a Python Script

You can also use the package in your own Python script:

```python
from linkedin_search_job.scraper import scrape_jobs

# Define your parameters
job_keyword = "AngularJS"
location = 'UnitedStates'
f_WT = "1,2"  # Work type: 1 for Onsite, 2 for Hybrid, 3 for Remote
f_JT = "F,P"  # Job type: F for Full-time, P for Part-time, C for Contract, T for Temporary, V for Volunteer
f_E = "5"     # Experience level: 1 for Internship, 2 for Entry level, 3 for Associate, 4 for Director, 5 for Executive
f_SB2 = '4'   # Salary: 1 for $40,000, 2 for $60,000, 3 for $80,000, 4 for $100,000, 5 for $120,000 (only one value allowed)
start = "0"   # Pagination: 0 for the first 10 results, 9 for the next 10, 18 for the next 10, and so on

# Call the function
jobs = scrape_jobs(job_keyword, location, f_WT, f_JT, f_E, f_SB2, start)

# Process the results
for job in jobs:
    print(f"Job Title: {job['title']}")
    print(f"Company: {job['company']}")
    print(f"Location: {job['location']}")
    print(f"Job Link: {job['job_link']}")
    print('---')
```

### Parameters

- `job_keyword`: The job keyword to search for (e.g., "Angular developer").
- `location`: The location to search in (e.g., "UnitedStates").
- `f_WT`: Work type. Use comma-separated values for multiple filters.
  - 1: Onsite
  - 2: Hybrid
  - 3: Remote
- `f_JT`: Job type. Use comma-separated values for multiple filters.
  - F: Full-time
  - P: Part-time
  - C: Contract
  - T: Temporary
  - V: Volunteer
- `f_E`: Experience level. Use comma-separated values for multiple filters.
  - 1: Internship
  - 2: Entry level
  - 3: Associate
  - 4: Director
  - 5: Executive
- `f_SB2`: Salary. Only one value allowed.
  - 1: $40,000
  - 2: $60,000
  - 3: $80,000
  - 4: $100,000
  - 5: $120,000
- `start`: Pagination. Start from 0 for the first 10 results, 9 for the next 10, 18 for the next 10, and so on.

### Example

To search for "AngularJS" jobs in the United States, with work types as Onsite or Hybrid, job types as Full-time or Part-time, executive level experience, a salary of $100,000, and starting from the first page:

```python
job_keyword = "AngularJS"
location = 'UnitedStates'
f_WT = "1,2"
f_JT = "F,P"
f_E = "5"
f_SB2 = '4'
start = "0"

# Call the function
jobs = scrape_jobs(job_keyword, location, f_WT, f_JT, f_E, f_SB2, start)

# Process the results
for job in jobs:
    print(f"Job Title: {job['title']}")
    print(f"Company: {job['company']}")
    print(f"Location: {job['location']}")
    print(f"Job Link: {job['job_link']}")
    print('---')
```

If you want to filter by multiple values, pass the argument values separated by commas. For pagination, pass 0 to get the first 10 records, then pass 9 to get the next 10 records, and so on.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
```

