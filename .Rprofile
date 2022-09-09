#----------------------------------------------#
# Author: Laurent Berge
# Date creation: Fri Sep  9 09:24:06 2022
# ~: auto copy style files
#----------------------------------------------#


m_time_css = file.mtime("ub_theme.css")
m_time_html = file.mtime("ub_theme.html")

m_time_tuto_css = file.mtime("UB_tutorial/ub_theme.css")
m_time_tuto_html = file.mtime("UB_tutorial/ub_theme.html")

any_update = FALSE

if(m_time_tuto_css < m_time_css){
	any_update = TRUE
	file.copy("ub_theme.css", "UB_tutorial/ub_theme.css", overwrite = TRUE)
}

if(m_time_tuto_html < m_time_html){
	any_update = TRUE
	file.copy("ub_theme.html", "UB_tutorial/ub_theme.html", overwrite = TRUE)
}

if(any_update){
	rmarkdown::render("UB_tutorial/UB_tutorial.Rmd")
}

# Now the html

m_time_tuto_html_main = file.mtime("UB_tutorial/UB_tutorial.html")
m_time_tuto_html = file.mtime("UB_tutorial.html")

if(m_time_tuto_html < m_time_tuto_html_main){
	file.copy("UB_tutorial/UB_tutorial.html", "UB_tutorial.html", overwrite = TRUE)
}


