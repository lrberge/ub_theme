



build_md_site = function(){
	rmarkdown::render_site(encoding = 'UTF-8')
	
	Sys.sleep(0.5)
	
	file.copy(list.files("_site/", full.names = TRUE), 
			  "docs/", 
			  recursive = TRUE)
	
}




