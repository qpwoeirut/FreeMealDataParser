# FreeMealDataParser

## Summary
This is a quick program written for OpenBrackets outreach efforts.
It parses a spreadsheet of Free Meal Data from the California Department of Education [website](https://www.cde.ca.gov/ds/ad/filessp.asp).
The spreadsheet has per-school statistics, which are transformed into per-district statistics.

## Process
The parser generates [district_free_meal_percentages.txt](/district_free_meal_percentages.txt), a list of all California school districts sorted by Free Meal percentages, and [bay_area_sorted.txt](/bay_area_sorted.txt), a list of just Bay Area school districts.
Bay Area schools districts are determined with the [bay_area_districts.txt](/bay_area_districts.txt) list, which is from [KRON4](https://www.kron4.com/community/schools/list-bay-area-school-districts-back-to-school-plans/).
The following code was used to scrape the district names.
```
const elems = document.querySelectorAll('a[rel="noreferrer noopener"] > strong, strong > a[rel="noreferrer noopener"]')
let s = "";
for (elem of elems) {
    if (elem.textContent.contains("District")) {
        s += elem.textContent + '\n'
    }
console.log(s)
}
```

The district names in the sheet and in the list are slightly different, so the parser checks if one of them is a substring of the other.
This causes some issues, which have been manually dealt with.
In particular, some districts match when they should not (e.g. "San Francisco" matching "South San Francisco").
Other districts do not match at all. Those required changing the names in the [bay_area_districts.txt](/bay_area_districts.txt) file.
Here is a list of those changes:
* `Tamalpais Unified School District` to `Tamalpais Union High`
* `Piner Olivet Union Elementary School District` to `Piner-Olivet Union Elementary School District`
* `Moraga Unified School District` to `Moraga School District`
* `Albany Unified School District` to `Albany City Unified School District`
* `Piedmont Unified School District` to `Piedmont City Unified School District`
* `Franklin-McKinley Union School District` to `Franklin-McKinley Elementary School District`
* `Campbell Unified School District` to `Campbell Union School District`
* `Mountain View Los Altos Union High School District` to `Mountain View-Los Altos Union High School District`
* `Mt. Pleasant Elementary School District` to `Mount Pleasant Elementary School District`
* `Live Oak School District` split into `Live Oak Unified School District` and `Live Oak Elementary School District`

Once the [bay_area_sorted.txt](/bay_area_sorted.txt) file was created, I took the top few from the sorted list as outreach targets.
A few of the schools were skipped. Those schools are listed below, along with the reason for omission.
* Bellevue Union is elementary school students.
* Live Oak Elementary is mostly elementary school students but also has a middle school? Might be worth looking at?
* Bayshore Elementary is one elementary school, I think.
