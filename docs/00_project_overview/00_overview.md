# Applied Engineering Exercise 01 — Groundwater Pumping Test

## 1. Assignment Information

| Item | Description |
|------|-------------|
| Assignment | Groundwater Pumping Test |
| Discipline | Hydrogeology |
| Subject | Python File Handling |
| Application | Groundwater Pumping Test Data Management |
| Difficulty | Foundational |
| Development Environment | Spyder |
| Programming Language | Python 3.12 |
| Unit System | US Customary |
| Implementation | Independent |

---

## 2. Objective

Develop a Python program that processes simulated groundwater
pumping test observations and generates a structured engineering
report in a plain text file.

The primary objective is to develop proficiency in Python file
handling while applying fundamental programming concepts to a
realistic engineering problem.

The exercise focuses on data management, numerical formatting,
basic engineering calculations, and report generation rather
than groundwater model development.

### 2.1 Learning Objectives

- Create and open text files.
- Write strings and numerical values to files.
- Apply numerical formatting.
- Organize engineering data into structured reports.
- Store and process observational datasets.
- Perform basic engineering calculations.
- Append additional observations to existing files.
- Read and display completed reports.
- Properly close files.
- Independently verify computational results.

---

## 3. Engineering Background

A constant-rate pumping test is conducted to investigate the
hydraulic characteristics of a confined aquifer.

Groundwater is extracted from a pumping well at a constant
discharge rate. Water levels are measured periodically at an
observation well located a known distance from the pumping well.

As pumping continues, the groundwater level at the observation
well declines in response to groundwater extraction.

The difference between the initial groundwater level and the
measured groundwater level during pumping is referred to as
drawdown.

Recorded groundwater drawdown observations can subsequently
be used to evaluate aquifer properties, including:

- Transmissivity
- Storativity
- Hydraulic conductivity
- Aquifer response to pumping

Aquifer parameter estimation is outside the scope of this
assignment.

All field observations provided in this exercise are synthetic
and are intended for educational purposes.

---

## 4. Project Information

| Parameter | Value |
|-----------|-------|
| Project Name | Confined Aquifer Pumping Test |
| Project Number | GW-001 |
| Test Number | PT-001 |
| Location | Hypothetical Research Site |
| Aquifer Type | Confined |
| Test Type | Constant-Rate Pumping Test |

---

## 5. Pumping Test Parameters

| Parameter | Value | Units |
|-----------|------:|-------|
| Pumping Well ID | PW-01 | — |
| Observation Well ID | OW-01 | — |
| Pumping Rate | 500 | gpm |
| Observation Well Distance | 150 | ft |
| Aquifer Thickness | 75 | ft |
| Initial Depth to Water | 25.00 | ft |
| Planned Test Duration | 1,440 | min |
| Planned Test Duration | 24 | hr |

Depth to water is measured vertically downward from a fixed
measuring point at the observation well.

The pumping rate is assumed to remain constant throughout
the pumping test.

---

## 6. Simulated Field Observations

### 6.1 Initial Observation Dataset

The following observations represent the first 720 minutes
of the pumping test.

| Observation | Elapsed Time (min) | Depth to Water (ft) | Pumping Rate (gpm) |
|------------:|-------------------:|--------------------:|-------------------:|
| 1 | 0 | 25.00 | 0 |
| 2 | 1 | 25.12 | 500 |
| 3 | 2 | 25.38 | 500 |
| 4 | 5 | 26.15 | 500 |
| 5 | 10 | 27.05 | 500 |
| 6 | 15 | 27.68 | 500 |
| 7 | 30 | 28.84 | 500 |
| 8 | 60 | 30.10 | 500 |
| 9 | 120 | 31.42 | 500 |
| 10 | 240 | 32.76 | 500 |
| 11 | 480 | 34.12 | 500 |
| 12 | 720 | 34.91 | 500 |

The zero-minute observation represents the pre-pumping
groundwater condition immediately before pumping begins.

### 6.2 Additional Observation Dataset

Assume the following observations become available after
the preliminary pumping test report has been generated.

| Observation | Elapsed Time (min) | Depth to Water (ft) | Pumping Rate (gpm) |
|------------:|-------------------:|--------------------:|-------------------:|
| 13 | 900 | 35.35 | 500 |
| 14 | 1,080 | 35.71 | 500 |
| 15 | 1,260 | 36.02 | 500 |
| 16 | 1,440 | 36.28 | 500 |

These observations will be appended to the existing report
during a subsequent file operation.

### 6.3 Data Storage Requirements

Select an appropriate Python data structure for storing
the field observations.

The selected structure should support:

- Multiple observation records.
- Consistent organization of observation parameters.
- Iteration through the dataset.
- Calculation of drawdown for individual observations.
- Addition of subsequent observations.
- Calculation of summary statistics.
- Formatted output to a text file.

The selection and implementation of the data structure are
left to the student.

---

## 7. Engineering Calculations

### 7.1 Groundwater Drawdown

Calculate groundwater drawdown for each observation.

$$
s_i = d_i - d_0
$$

Where:

| Symbol | Description | Units |
|--------|-------------|-------|
| $s_i$ | Drawdown at observation i | ft |
| $d_i$ | Measured depth to water at observation i | ft |
| $d_0$ | Initial depth to water | ft |

Because depth to water is measured positively downward,
an increase in measured depth represents a decline in
groundwater level.

### 7.2 Total Groundwater Extraction Volume

Calculate the total volume of groundwater extracted during
the pumping test.

For constant-rate pumping:

$$
V = Qt
$$

Where:

| Symbol | Description | Units |
|--------|-------------|-------|
| $V$ | Total groundwater extraction volume | gal |
| $Q$ | Constant pumping rate | gpm |
| $t$ | Elapsed pumping time | min |

The zero-minute observation represents the pre-pumping
condition. Constant-rate pumping begins immediately
after this observation.

### 7.3 Maximum Drawdown

Determine the maximum recorded drawdown.

$$
s_{\max} = \max(s_1, s_2, \ldots, s_n)
$$

### 7.4 Minimum Drawdown

Determine the minimum recorded drawdown.

$$
s_{\min} = \min(s_1, s_2, \ldots, s_n)
$$

Include the initial pre-pumping observation in the
calculation.

### 7.5 Average Recorded Drawdown

Calculate the arithmetic mean of the recorded drawdown
observations.

$$
\bar{s} = \frac{1}{n}\sum_{i=1}^{n}s_i
$$

Where:

| Symbol | Description |
|--------|-------------|
| $\bar{s}$ | Arithmetic mean of recorded drawdown |
| $s_i$ | Individual drawdown observation |
| $n$ | Number of observations |

Because observations are collected at irregular time
intervals, this arithmetic mean is not equivalent to
a time-weighted average drawdown.

A time-weighted average is outside the primary scope
of this assignment.

### 7.6 Final Drawdown

Determine the drawdown associated with the final
observation in the dataset.

### 7.7 Observation Count

Determine the total number of observation records,
including the initial pre-pumping observation.

### 7.8 Elapsed Pumping Time

Determine the elapsed pumping time associated with
the final observation.

---

## 8. Output File Requirements

| Item | Requirement |
|------|-------------|
| Output Directory | `outputs/` |
| Filename | `groundwater_pumping_test.txt` |
| File Format | Plain text |
| Character Encoding | UTF-8 |
| Unit System | US Customary |

The output file shall be generated programmatically.

The report shall not require manual editing after
generation.

---

## 9. Engineering Report Structure

The completed report shall contain the following headings.

### Report Title

    GROUNDWATER PUMPING TEST REPORT

### Section 1 — Project Information

Include:

- Project name
- Project number
- Test number
- Project location
- Aquifer type
- Test type

### Section 2 — Pumping Test Parameters

Include:

- Pumping well identification
- Observation well identification
- Constant pumping rate
- Observation well distance
- Aquifer thickness
- Initial depth to water
- Planned pumping test duration

### Section 3 — Groundwater Level Observations

Include the initial field observations collected
during the first 720 minutes of testing.

Required columns:

- Observation number
- Elapsed time
- Pumping rate
- Measured depth to water

### Section 4 — Drawdown Calculations

Include the calculated drawdown associated with
each initial observation.

Required columns:

- Observation number
- Elapsed time
- Measured depth to water
- Calculated drawdown

### Section 5 — Preliminary Pumping Test Summary

Include:

- Number of observations
- Elapsed pumping time
- Maximum recorded drawdown
- Minimum recorded drawdown
- Average recorded drawdown
- Final recorded drawdown
- Total groundwater extraction volume

The preliminary summary shall represent the first
720 minutes of the pumping test.

### Section 6 — Additional Field Observations

Include the additional observations collected
between 900 and 1,440 minutes.

Required columns:

- Observation number
- Elapsed time
- Pumping rate
- Measured depth to water
- Calculated drawdown

### Section 7 — Updated Pumping Test Summary

Include:

- Total number of observations
- Total elapsed pumping time
- Maximum recorded drawdown
- Minimum recorded drawdown
- Average recorded drawdown
- Final recorded drawdown
- Total groundwater extraction volume

The updated summary shall include both the initial
and additional field observations.

### Section 8 — Engineering Notes

Include the assumptions and limitations identified
in Section 13 of this assignment.

---

## 10. Numerical Formatting Requirements

| Parameter | Formatting Requirement |
|-----------|------------------------|
| Observation Number | Integer |
| Elapsed Time | Integer |
| Pumping Rate | One decimal place |
| Depth to Water | Two decimal places |
| Drawdown | Two decimal places |
| Average Drawdown | Two decimal places |
| Extraction Volume | Integer with thousands separators |
| Numerical Alignment | Right aligned |
| Text Alignment | Left aligned |

Additional formatting requirements:

- Provide descriptive column headings.
- Identify engineering units.
- Maintain consistent column widths.
- Include horizontal separators.
- Separate report sections using blank lines.
- Maintain consistent numerical precision.
- Ensure the report is readable in a standard text editor.

Numerical rounding should be applied during output
formatting rather than during intermediate calculations.

---

## 11. Implementation Requirements

### 11.1 Establish Project Parameters

Define the project information and engineering parameters
required to generate the report.

### 11.2 Establish Initial Observation Dataset

Store the initial 12 field observations using an
appropriate Python data structure.

### 11.3 Perform Initial Engineering Calculations

Calculate:

- Drawdown for each observation.
- Preliminary summary statistics.
- Preliminary extraction volume.

### 11.4 Create Initial Report

Open the output file using write mode.

Generate the following report sections:

1. Report title.
2. Project information.
3. Pumping test parameters.
4. Groundwater level observations.
5. Drawdown calculations.
6. Preliminary pumping test summary.

Close the file after completing the initial report.

### 11.5 Establish Additional Observation Dataset

Store the four additional field observations.

Preserve the initial observation dataset.

### 11.6 Perform Updated Engineering Calculations

Calculate drawdown for the additional observations.

Calculate updated summary statistics using the
complete dataset of 16 observations.

### 11.7 Append Additional Information

Reopen the existing output file using append mode.

Append:

1. Additional field observations.
2. Additional calculated drawdown values.
3. Updated pumping test summary.
4. Engineering notes.

Preserve all previously written report information.

Close the file after completing the additional entries.

### 11.8 Read Completed Report

Reopen the completed report using read mode.

Read the contents of the report and display them
in the Spyder console.

Close the file after completing the read operation.

### 11.9 Independent Verification

Compare the calculated results against the
verification values provided in Section 14.

Investigate and resolve discrepancies before
considering the exercise complete.

---

## 12. Suggested Python Script Headings

Organize the Python script using descriptive comment
headings or Spyder code cells.

The following headings are recommended:

1. Module Documentation
2. Imports
3. Output File Configuration
4. Project Information
5. Pumping Test Parameters
6. Initial Observation Dataset
7. Initial Drawdown Calculations
8. Preliminary Summary Statistics
9. Write Initial Report
10. Additional Observation Dataset
11. Additional Drawdown Calculations
12. Updated Summary Statistics
13. Append Additional Report Information
14. Read Completed Report
15. Verification
16. End of Script

The implementation beneath each heading shall be
developed independently.

No implementation code is provided as part of
this assignment.

---

## 13. Engineering Assumptions and Limitations

Include the following assumptions and limitations
in the generated engineering report:

- All groundwater observations are synthetic.
- The aquifer is assumed to be confined.
- The pumping rate is assumed to remain constant.
- Pumping begins immediately after the initial observation.
- Depth to water is measured from a fixed measuring point.
- No corrections have been applied for barometric pressure.
- No corrections have been applied for regional groundwater
  level fluctuations.
- No corrections have been applied for other pumping wells.
- Aquifer transmissivity has not been estimated.
- Aquifer storativity has not been estimated.
- Aquifer boundary conditions have not been evaluated.
- The observations were not generated from a calibrated
  groundwater flow model.
- The results are intended for educational purposes only.

---

## 14. Verification Criteria

### 14.1 Selected Drawdown Values

| Elapsed Time (min) | Expected Drawdown (ft) |
|-------------------:|-----------------------:|
| 0 | 0.00 |
| 1 | 0.12 |
| 5 | 1.15 |
| 30 | 3.84 |
| 60 | 5.10 |
| 120 | 6.42 |
| 480 | 9.12 |
| 720 | 9.91 |
| 900 | 10.35 |
| 1,440 | 11.28 |

### 14.2 Preliminary Summary Verification

| Parameter | Expected Value |
|-----------|---------------:|
| Observation Count | 12 |
| Elapsed Pumping Time (min) | 720 |
| Minimum Drawdown (ft) | 0.00 |
| Maximum Drawdown (ft) | 9.91 |
| Average Recorded Drawdown (ft) | 4.43 |
| Final Drawdown (ft) | 9.91 |
| Extraction Volume (gal) | 360,000 |

### 14.3 Final Summary Verification

| Parameter | Expected Value |
|-----------|---------------:|
| Observation Count | 16 |
| Elapsed Pumping Time (min) | 1,440 |
| Minimum Drawdown (ft) | 0.00 |
| Maximum Drawdown (ft) | 11.28 |
| Average Recorded Drawdown (ft) | 6.02 |
| Final Drawdown (ft) | 11.28 |
| Extraction Volume (gal) | 720,000 |

Average drawdown values represent the arithmetic mean
of all recorded observations, including the initial
pre-pumping observation.

### 14.4 File Verification

Verify that:

- The output file exists.
- The output file contains the required report headings.
- Numerical columns are properly aligned.
- Engineering units are clearly identified.
- Initial observations were written successfully.
- Additional observations were appended successfully.
- Previously written information was preserved.
- Updated summary statistics include all observations.
- The completed report can be read successfully.
- All opened files have been properly closed.

---

## 15. Deliverables

### 15.1 Required Deliverables

| Deliverable | Filename |
|-------------|----------|
| Assignment Scope | `01_groundwater_pumping_test.md` |
| Python Implementation | `groundwater_pumping_test.py` |
| Generated Engineering Report | `groundwater_pumping_test.txt` |

### 15.2 Optional Deliverables

- Learning log entry.
- Computational verification notes.
- Scientific figures.
- Additional experimental scripts.
- CSV observation dataset.

Generated output files may be excluded from version
control using the repository's `.gitignore` configuration.

---

## 16. Assignment Completion Checklist

### Project Setup

- [ ] Create Python exercise script.
- [ ] Establish script comment headings.
- [ ] Identify output directory.
- [ ] Identify output filename.
- [ ] Confirm working directory.

### Data Management

- [ ] Define project information.
- [ ] Define pumping test parameters.
- [ ] Store initial observation dataset.
- [ ] Store additional observation dataset.
- [ ] Preserve initial observation records.

### Engineering Calculations

- [ ] Calculate initial drawdown values.
- [ ] Calculate additional drawdown values.
- [ ] Calculate preliminary observation count.
- [ ] Calculate preliminary summary statistics.
- [ ] Calculate preliminary extraction volume.
- [ ] Calculate updated observation count.
- [ ] Calculate updated summary statistics.
- [ ] Calculate final extraction volume.

### File Handling

- [ ] Open output file using write mode.
- [ ] Write report title.
- [ ] Write project information.
- [ ] Write pumping test parameters.
- [ ] Write initial observations.
- [ ] Write initial drawdown calculations.
- [ ] Write preliminary summary.
- [ ] Close initial report.
- [ ] Reopen report using append mode.
- [ ] Append additional observations.
- [ ] Append additional drawdown calculations.
- [ ] Append updated summary.
- [ ] Append engineering notes.
- [ ] Close updated report.
- [ ] Reopen completed report using read mode.
- [ ] Display report in Spyder console.
- [ ] Close completed report.

### Verification

- [ ] Verify selected drawdown calculations.
- [ ] Verify preliminary summary statistics.
- [ ] Verify updated summary statistics.
- [ ] Verify preliminary extraction volume.
- [ ] Verify final extraction volume.
- [ ] Verify numerical formatting.
- [ ] Verify engineering units.
- [ ] Verify preservation of initial observations.
- [ ] Verify proper file closure.

### Documentation

- [ ] Document significant learning observations.
- [ ] Document encountered errors and resolutions.
- [ ] Document engineering assumptions.
- [ ] Record potential improvements.
- [ ] Commit completed implementation to version control.

---

## 17. Optional Extensions

The following investigations are optional and are not
required to complete the primary assignment.

### 17.1 Additional File Handling

- Read the file one line at a time.
- Read a specified number of characters.
- Read all lines into a list.
- Investigate file positioning.
- Investigate file buffering.
- Compare explicit file closure with context managers.

### 17.2 Filesystem Management

- Investigate relative and absolute file paths.
- Investigate pathlib.
- Handle missing output directories.
- Check whether an output file already exists.
- Prevent accidental overwriting of previous reports.

### 17.3 Exception Handling

Investigate handling of:

- FileNotFoundError
- FileExistsError
- PermissionError
- ValueError
- OSError

### 17.4 Scientific Data Export

Export the groundwater observation dataset to:

- CSV
- JSON
- NumPy-compatible text files

### 17.5 Scientific Visualization

Develop the following figures:

- Drawdown versus elapsed time.
- Depth to water versus elapsed time.
- Drawdown versus logarithmic elapsed time.
- Cumulative groundwater extraction volume versus time.

Exclude the zero-minute observation when plotting
against logarithmic elapsed time.

### 17.6 Additional Numerical Investigations

- Calculate the time-weighted average drawdown.
- Investigate numerical integration of drawdown over time.
- Calculate drawdown rates between observations.
- Investigate sensitivity to measurement precision.
- Investigate the effect of missing observations.

---

## 18. Future Research Applications

The observation dataset may serve as a starting point
for subsequent hydrogeological investigations.

Potential future exercises include:

| Investigation | Scientific or Numerical Method |
|---------------|--------------------------------|
| Aquifer parameter estimation | Curve fitting |
| Pumping test interpretation | Cooper-Jacob approximation |
| Analytical drawdown modeling | Theis solution |
| Transmissivity estimation | Linear regression |
| Storativity estimation | Inverse modeling |
| Aquifer parameter calibration | Numerical optimization |
| Measurement uncertainty | Statistical analysis |
| Aquifer property uncertainty | Monte Carlo simulation |
| Groundwater flow simulation | Finite difference methods |

Because the supplied observations are illustrative rather
than physically calibrated, subsequent aquifer parameter
estimation should be treated as a numerical experiment.

A separate physically consistent dataset may be developed
for formal verification of analytical groundwater models.

---

## 19. Python Concepts

| Concept | Engineering Application |
|---------|-------------------------|
| Variables | Engineering parameters |
| Strings | Project information |
| Lists | Observation datasets |
| Tuples | Individual observation records |
| Dictionaries | Structured engineering information |
| Arithmetic | Drawdown and extraction calculations |
| Loops | Processing observation records |
| String formatting | Engineering report tables |
| File opening | Accessing research files |
| File writing | Generating engineering reports |
| File appending | Recording subsequent observations |
| File reading | Retrieving completed reports |
| File closure | Resource management |
| Verification | Independent engineering checks |

---

## 20. References

### Python

- Python Documentation — Reading and Writing Files
  https://docs.python.org/3/tutorial/inputoutput.html

- Python Documentation — Built-in Functions
  https://docs.python.org/3/library/functions.html#open

- Python Documentation — I/O Tools
  https://docs.python.org/3/library/io.html

- Python Documentation — pathlib
  https://docs.python.org/3/library/pathlib.html

### Hydrogeology

- Freeze, R. A., and Cherry, J. A. Groundwater.

- Fetter, C. W. Applied Hydrogeology.

- The Groundwater Project
  https://gw-project.org/

- United States Geological Survey
  https://www.usgs.gov/

### Numerical Methods

- Kiusalaas, J. Numerical Methods in Engineering with Python 3.
  Third Edition. Cambridge University Press, 2013.

---

**Assignment Category:** Applied Engineering

**Research Discipline:** Hydrogeology

**Primary Learning Topic:** Python File Handling

**Secondary Learning Topics:** Data Structures, Numerical
Formatting, Engineering Calculations, Computational Verification

**Implementation Approach:** Independent Scientific Programming

**Status:** Not Started
