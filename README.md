# Module11debuging-and-defensiveprograming-in-r
For the assignment this week, we were given a deliberately flawed piece of code, and were asked to attempt to debug it, and then report back on our success or failure. Unfortunately, while I believe I have found the nature of the error, I have not figured out how to fix it. Looking at the flawed code: 

tukey_multiple <- function(x) {
   outliers <- array(TRUE,dim=dim(x))
   for (j in 1:ncol(x))
    {
    outliers[,j] <- outliers[,j] && tukey.outlier(x[,j])
    }
outlier.vec <- vector(length=nrow(x))
    for (i in 1:nrow(x))
    { outlier.vec[i] <- all(outliers[i,]) } return(outlier.vec) }
    
I first attempted to run it, in order to see what sort of error message would come up. Trying it a few times to make sure, I was able to confirm that the issue seemed to be the bit of code regarding the "i"s near the end, with Rstudio seeming to regard them as "unexpected symbols" in a way that prevented it from running the code. I attempted to use the functions mentioned in the lecture and readings, such as debug() and trackback(), but one wrinkle that didn't seem apparent during my studying is that all these resources recomended seem to be catering towards errors in functions that are already properly designed and ready to deploy, while the code listed here cannot become a proper function due to the way that Rstudio refuses to let it run to the end due to the error, meaning that I was unable to make use of those resources. While I was able to create a function that could run to the end by excising the failing aspects, this will not help figure out how to fix the unexpected symbols and create a functioning function. 
