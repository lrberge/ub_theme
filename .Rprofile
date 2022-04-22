



build_md_site = function(){
	rmarkdown::render_site(encoding = 'UTF-8')
	
	Sys.sleep(0.5)
	
	file.remove("docs/")
	
	Sys.sleep(0.5)
	
	file.rename("_site/", "docs/")
	
}




