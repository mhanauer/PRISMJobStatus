setwd("~/Box Sync/Unreviewed Excel Training Data/ Matt'sExcelTraining Data")
library(XLConnect)

dat1 = readWorksheetFromFile("Boys + Girls Club Camp Training 2016.xlsx", sheet = 1, startCol = 1, endCol = 1)
colnames(dat1) = c("Job")
head(dat1)

dat2 = readWorksheetFromFile("IU Pre School Training 12716.xlsx", sheet = 1, startCol = 1, endCol = 1)
colnames(dat2) = c("Job")
head(dat2)

dat3 = readWorksheetFromFile("Ivy Tech 2017 Training.xlsx", sheet = 1, startCol = 1, endCol = 1)
colnames(dat3) = c("Job")
head(dat3)

dat4 = readWorksheetFromFile("Janet Decker Law Class.xlsx", sheet = 2, startCol = 1, endCol = 1)
colnames(dat4) = c("Job")
head(dat4)

dat5 = readWorksheetFromFile("MCCSC LGBTQA+ Competency Training_assessment data.xlsx", sheet = 1, startCol = 2, endCol = 2)
colnames(dat5) = c("Job")
head(dat5)

dat6 = readWorksheetFromFile("MCCSC LGBTQA+ Competency Training_assessment data.xlsx", sheet = 2, startCol = 2, endCol = 2)
colnames(dat6) = c("Job")
head(dat6)

dat7 = readWorksheetFromFile("MCCSC LGBTQA+ Competency Training_assessment data.xlsx", sheet = 2, startCol = 2, endCol = 2)
colnames(dat7) = c("Job")
head(dat7)

dat8 = readWorksheetFromFile("Merriville Training 7272016.xlsx", sheet = 1, startCol = 1, endCol = 1)
dat8 = as.data.frame(dat8)# This gets rid of the first row for a one column
colnames(dat8) = c("Job")
head(dat8)

dat9 = readWorksheetFromFile("MCCSC LGBTQA+ Competency Training_assessment data.xlsx", sheet = 2, startCol = 2, endCol = 2)
colnames(dat9) = c("Job")
head(dat9)

dat = rbind(dat1, dat2, dat3, dat4, dat5, dat6, dat7, dat8, dat9)
dat$ID = 1:nrow(dat)
datLevels = as.factor(dat$Job)
levels(datLevels)
#### Grab total teachers, then elementary, then middle + high, then admin,  then college student
