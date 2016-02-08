Name <- c("Winston", "Manning")

attempts <- c(535, 331)
completions <- c(312, 198)
total_yards <- c(4042, 2249)
touch_downs <- c(22, 9)
interceptions <- c(15, 17)

att = attempts
comp = completions
yds = total_yards
td = touch_downs
int = interceptions

stat <- data.frame(Name, att, comp, yds, td, int)


a <- ((comp/att)-0.3)*5

b <- ((yds/att)-3)*0.25

c <- (td/att)*20

d <- 2.375-((int/att)*25)

r1 <- function(r)
  ((a+b+c+d)/6)*100
r1()

results <- apply(stat[1,1:6],1,r1)
rating <- c(results)
rating
QB_Stats <- cbind(stat, rating)
QB_Stats

