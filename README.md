# R_for_fun
#Punning,Easy,R-programming

#This is what you want to input R for the first time.

#[Step0]
#download & install the packages
install.packages("ggplot2") 
install.packages('reshape2')

#[Step1]
#reload the packages
library('ggplot2')
library(reshape2)

#[Step2]
#read the data
data<-read.table("D:\\RRR\\R_for_Fun\\data\\_01_HeatMap.txt",header=T)
head(data)

#[Step3]
#reshape & dealing
data<-melt(data,id.var = "Num",variable.name = "type",value.name = "Re.Q")
head(data)
g = ggplot(data, aes(x=Num, y=type, fill=Re.Q))
xlab("X-labels")
ylab("Y-labels")
g1=g+geom_tile(color="white", size=0.1)

#[Step4]
#print the plot
print(g1)
