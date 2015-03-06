# Code
dat <- read.csv("femaleMiceWeights.csv")
dat[1:12,2]
mean(dat[13:24,2]) - mean(dat[1:12,2])
s = split(dat[,2], dat[,1])
stripchart(split(dat[,2], dat[,1]), vertical=TRUE, col=1:2)
abline(h=sapply(split(dat[,2], dat[,1]), mean), col=1:2)
highfat <- split(dat[,2], dat[,1])[["hf"]]
print (highfat)
sample(highfat, 6)
The function sample() goes into the 'highfat' vector and chooses 6 values at random (6 is the second argument to sample, which is called the 'size' of the sample). 
sample() called 'replace' which toggles whether or not an observation can be chosen more than once (whether to replace the observations back in the population after they are chosen once). The default setting for 'replace' is set to FALSE, so if we don't say anything, the sample() function will not choose an observation more than once.
sample(highfat, 6, replace=TRUE)
highfat  > 30
as.numeric(highfat > 30)
For example if we want to know the number of the high fat diet mice that weigh over 30:
sum(highfat > 30)
mean((highfat > 30))
