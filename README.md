`Tamalpais Unified School District` to `Tamalpais Union High`
`Piner Olivet Union Elementary School District` to `Piner-Olivet Union Elementary School District`
`Moraga Unified School District` to `Moraga School District`
`Albany Unified School District` to `Albany City Unified School District`
`Piedmont Unified School District` to `Piedmont City Unified School District`
`Franklin-McKinley Union School District` to `Franklin-McKinley Elementary School District`
`Campbell Unified School District` to `Campbell Union School District`
`Mountain View Los Altos Union High School District` to `Mountain View-Los Altos Union High School District`
`Mt. Pleasant Elementary School District` to `Mount Pleasant Elementary School District`
`Live Oak School District` split into `Live Oak Unified School District` and `Live Oak Elementary School District`

https://www.kron4.com/community/schools/list-bay-area-school-districts-back-to-school-plans/
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

* Bellevue Union is elementary school students.
* Live Oak Elementary is mostly elementary school students but also has a middle school? Might be worth looking at?
* Bayshore Elementary is one elementary school, I think.
