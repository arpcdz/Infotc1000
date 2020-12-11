# Code Sample

I wrote this R Studio code for a project final last semester to analyze a dataset.


>setwd("/Users/adriennepyeatt/Downloads/my_stats_project")
>titanic = read.csv(“titanic.csv”)
>head(titanic)
>any(is.na(titanic)) 
>titanic = na.omit(titanic)
>summary(titanic)
> titanic = within(titanic, remove(PassengerId, Name, Ticket, Cabin))
> summary(titanic)
>str(titanic)
> titanic$Survived->Survived
> titanic$Pclass->Pclass
> titanic$Sex->Sex
> titanic$Age->Age
> titanic$SibSp->SibSp
> titanic$Parch->Parch
> titanic$Fare->Fare
> titanic$Embarked->Embarked

>plot(Pclass,Survived, main = "Scatterplot between Passenger Class and Survived", xlab = "Passenger Class")
> plot(Age,Survived, main = "Scatterplot between Age and Survived", xlab = "Age")
> plot(Pclass,Survived, main = "Scatterplot between Passenger Class and Survived", xlab = "Passenger Class")
> plot(Sex,Survived, main = "Scatterplot between Sex and Survived", xlab = "Sex")
> plot(SibSp,Survived, main = "Scatterplot between Number of Siblings and Spouses Aboard and Survived", xlab = "Number of Siblings and Spouses Aboard")
> plot(Parch,Survived, main = "Scatterplot between Number of Parents and Children Aboard and Survived", xlab = "Number of Parents and Children Aboard")


>titanic$Survived = factor(titanic$Survived)
>titanic$Pclass = factor(titanic$Pclass)
Graph codes


>indicators = model.matrix(~Pclass+Embarked+Sex, data=titanic)
>head(indicators)
>indicators = indicators[,-1]
>head(indicators)
>titanic = cbind(titanic, indicators)
>titanic = within(titanic, rm(Pclass, Embarked, Sex))
>head(titanic)


>correlations = cor(titanic[,-1])
#-1 because survived is the FIRST COLUMN and because it is the response variable we are not looking for correlations here when looking at multicollinearity
>correlations
#displacement and horsepower are highly correlated, so we should only use one or the other
#ALSO displacement and weight are highly correlated, so we should drop both horsepower and weight and just use displacement in our final model
> install.packages("corrplot")
>library(corrplot) 
> corrplot(correlations, method = "color", type = "lower")




[Continue on to my hobbies](./hobby.md) or
[return to home page](./README.md)
