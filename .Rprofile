#----------------------------------------------#
# Author: Laurent Berge
# Date creation: Fri Sep  9 09:24:06 2022
# ~: auto copy style files + auto render
#----------------------------------------------#


m_time_css = file.mtime("ub_theme.css")
m_time_html = file.mtime("ub_theme.html")

m_time_tuto_css = file.mtime("UB_tutorial/ub_theme.css")
m_time_tuto_html = file.mtime("UB_tutorial/ub_theme.html")

any_update = FALSE

if(m_time_tuto_css < m_time_css){
	any_update = TRUE
	message("ub_theme.css has been updated")
	file.copy("ub_theme.css", "UB_tutorial/ub_theme.css", overwrite = TRUE)
}

if(m_time_tuto_html < m_time_html){
	any_update = TRUE
	message("ub_theme.html has been updated")
	file.copy("ub_theme.html", "UB_tutorial/ub_theme.html", overwrite = TRUE)
}

if(any_update){
	message("rendering UB_tutorial")
	suppressPackageStartupMessages(library(rmarkdown))
	rmarkdown::render("UB_tutorial/UB_tutorial.Rmd")
}

# Now the html

m_time_tuto_html_main = file.mtime("UB_tutorial/UB_tutorial.html")
exist_tuto = file.exists("UB_tutorial.html")
if(exist_tuto) m_time_tuto_html = file.mtime("UB_tutorial.html")

if(!exist_tuto || m_time_tuto_html < m_time_tuto_html_main){
	message("UB_tutorial.html has been updated")
	file.copy("UB_tutorial/UB_tutorial.html", "UB_tutorial.html", overwrite = TRUE)
}


