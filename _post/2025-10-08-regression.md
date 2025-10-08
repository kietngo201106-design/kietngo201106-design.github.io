---
layout: post
---

# Load the PDF and extract text
doc = fitz.open("regression_practice.pdf")
pdf_text = ""
for page in doc:
    pdf_text += page.get_text()

# Create the markdown content
markdown_content = """---
layout: post
author: Abhinav Saxena
tags: [overview, moonwalk]
---

# Investigating the Titanic Dataset: A Regression Analysis Journey

Understanding the survival patterns of Titanic passengers has long been a classic data science problem. In this blog post, I walk through a detailed investigation of the Titanic dataset using logistic regression, inspired by a structured regression practice guide.

## Data Preparation and Cleaning

The dataset was first loaded and inspected. Missing values in the `Age` column were imputed using the average age grouped by `Sex` and `Pclass`. This approach avoids data leakage by not using the `Survived` column for imputation.
