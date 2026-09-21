# Practical Machine Learning Course Project

## Predicting Exercise Manner from Wearable Sensor Data

This repository contains my submission for the Johns Hopkins / Coursera **Practical Machine Learning** course project.

The goal is to predict the `classe` variable using wearable accelerometer measurements collected from the belt, arm, forearm, and dumbbell during barbell lifts.

## Files

- [PML_Course_Project.Rmd](PML_Course_Project.Rmd) — reproducible R Markdown source
- [PML_Course_Project.html](PML_Course_Project.html) — browser-viewable report
- [index.html](index.html) — GitHub Pages entry page
- [predictions.csv](predictions.csv) — predictions for the 20 quiz cases

## Method

The analysis:

1. removes metadata and highly incomplete variables;
2. removes near-zero-variance predictors;
3. creates a stratified 70/30 development-validation split;
4. tunes a Random Forest using 3-fold cross-validation;
5. evaluates the tuned model on the untouched validation set;
6. refits the selected model on all labelled observations; and
7. predicts the 20 official course test cases.

The exact validation accuracy and expected out-of-sample error are calculated automatically when the R Markdown is knitted.

## Quiz predictions

`B A B A A E D B A A B C B A E E A B B B`

## Reproducing the analysis

Install the required packages if needed:

```r
install.packages(c("caret", "randomForest", "knitr", "rmarkdown"))
```

Then open `PML_Course_Project.Rmd` in RStudio and click **Knit**, or run:

```r
rmarkdown::render("PML_Course_Project.Rmd")
```

The source file downloads the original course datasets directly and reproduces the preprocessing, cross-validation, validation, and final predictions.

## Data source

Velloso, E., Bulling, A., Gellersen, H., Ugulino, W., & Fuks, H. (2013). *Qualitative Activity Recognition of Weight Lifting Exercises*. Proceedings of the 4th Augmented Human International Conference.
