Project_1
=========
R Code: 

Rebecca <- read.table("~/Downloads/household_power_consumption.txt",header=T,sep=";",stringsAsFactors=FALSE)
attach(Rebecca)
###View(Rebecca)
Rebecca$Date2 <- as.Date(Rebecca$Date, format = "%d/%m/%Y")
###View(Rebecca)
newdata<-subset(Rebecca,Date2=="2007-02-02" | Date2=="2007-02-01",select=c(1:9))
###View(newdata)
###str(newdata)
#plot1<-hist(as.numeric(newdata$Global_active_power),col="red",main="Global Active Power",xlab="Global Active Power (kilowatts)",ylab="Frequency")
#hist(as.numeric(newdata$Global_active_power),col="red",main="Global Active Power",xlab="Global Active Power (kilowatts)",ylab="Frequency")

png(file="plot1.png")
with(newdata,hist(as.numeric(newdata$Global_active_power),col="red",xlab="Global Active Power (kilowatts)",ylab="Frequency"))
title(main="Global Active Power")
#dev.copy(device=quartz)
#plot(plot1)
dev.off()

Rebecca <- read.table("~/Downloads/household_power_consumption.txt",header=T,sep=";",stringsAsFactors=FALSE)
attach(Rebecca)
View(Rebecca)
Rebecca$Date2 <- as.Date(Rebecca$Date, format = "%d/%m/%Y")
###View(Rebecca)
newdata<-subset(Rebecca,Date2=="2007-02-02" | Date2=="2007-02-01",select=c(1:9))
View(newdata)

newdata$x <- paste(newdata$Date, newdata$Time)
newdata$x<-strptime(x, "%d/%m/%Y %H:%M:%S")
plot(newdata$x, newdata$Global_active_power, type="l",ylab="Global Active Power (kilowats)",xlab=NA)

png(file="plot2.png")
with(newdata,plot(newdata$x, newdata$Global_active_power, type="l",ylab="Global Active Power (kilowats)",xlab=NA))
#dev.copy(device=quartz)
#plot(plot2)
dev.off()

Rebecca <- read.table("~/Downloads/household_power_consumption.txt",header=T,sep=";",stringsAsFactors=FALSE)
attach(Rebecca)
#View(Rebecca)
Rebecca$Date2 <- as.Date(Rebecca$Date, format = "%d/%m/%Y")
###View(Rebecca)
newdata<-subset(Rebecca,Date2=="2007-02-02" | Date2=="2007-02-01",select=c(1:9))
#View(newdata)

newdata$x <- paste(newdata$Date, newdata$Time)
newdata$x<-strptime(x, "%d/%m/%Y %H:%M:%S")

png(file="plot3.png")
plot(newdata$x, newdata$Sub_metering_1, type="l",ylab="Energy sub metering",xlab=NA, col="black")
lines(newdata$x, newdata$Sub_metering_2,type="l",col="red")
lines(newdata$x, newdata$Sub_metering_3, type="l",col="blue")
legend("topright",pch=1,col=c("black","red","blue"),legend=c("Sub_metering_1","Sub_metering_2","Sub_metering_3"))
dev.off()

Rebecca <- read.table("~/Downloads/household_power_consumption.txt",header=T,sep=";",stringsAsFactors=FALSE)
attach(Rebecca)
#View(Rebecca)
Rebecca$Date2 <- as.Date(Rebecca$Date, format = "%d/%m/%Y")
###View(Rebecca)
newdata<-subset(Rebecca,Date2=="2007-02-02" | Date2=="2007-02-01",select=c(1:9))
#View(newdata)

newdata$x <- paste(newdata$Date, newdata$Time)
newdata$x<-strptime(x, "%d/%m/%Y %H:%M:%S")

png(file="plot4.png")
par(mfrow=c(2,2))
plot(newdata$x, newdata$Global_active_power, type="l",ylab="Global Active Power (kilowats)",xlab=NA)

plot(newdata$x, newdata$Voltage,ylab="Voltage",xlab="datetime",main=NA,type="l")

plot(newdata$x, newdata$Sub_metering_1, type="l",ylab="Energy sub metering",xlab=NA, col="black")
lines(newdata$x, newdata$Sub_metering_2,type="l",col="red")
lines(newdata$x, newdata$Sub_metering_3, type="l",col="blue")
legend("topright",pch=1,col=c("black","red","blue"),legend=c("Sub_metering_1","Sub_metering_2","Sub_metering_3"))

plot(newdata$x, newdata$Global_reactive_power,ylab="Global_reative_power",xlab="datetime",main=NA,type="l")

dev.off()




Project 1 Submission 
