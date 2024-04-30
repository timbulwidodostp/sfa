# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Spatial Stochastic Frontier Analysis models estimation Use ssfa With (In) R Software
install.packages("readxl")
install.packages("httr")
install.packages("ssfa")
library("httr")
library("readxl")
library("ssfa")
github_link <- "https://github.com/timbulwidodostp/sfa/raw/main/sfa_one/sfa_one.xlsx"
temp_file <- tempfile(fileext = ".xlsx")
req <- GET(github_link, 
# authenticate using GITHUB_PAT
authenticate(Sys.getenv("GITHUB_PAT"), ""),
# write result to disk
write_disk(path = temp_file))
sfa_one <- readxl::read_excel(temp_file)
github_link <- "https://github.com/timbulwidodostp/sfa/raw/main/sfa_two/sfa_two.xlsx"
temp_file <- tempfile(fileext = ".xlsx")
req <- GET(github_link, 
# authenticate using GITHUB_PAT
authenticate(Sys.getenv("GITHUB_PAT"), ""),
# write result to disk
write_disk(path = temp_file))
sfa_two <- readxl::read_excel(temp_file)
# Estimate Spatial Stochastic Frontier Analysis models estimation Use ssfa With (In) R Software
sfa<-ssfa(log_y~log_x,data=sfa_one,data_w=sfa_two,form ="production",par_rho=FALSE)
summary(sfa)
# Spatial Stochastic Frontier Analysis models estimation Use ssfa With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished