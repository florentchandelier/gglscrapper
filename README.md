gglscrapper
===========

How it works: Basically you create a GoogleScraper object with the query to search. You also specify the number of results per page (10,25,50 or 100) you want to obtain. Then you call the method search() on the new made object with a parameter indicating the number of pages too search for. I didn’t tried how many pages I can scrape^^ It’s up to you to tell me!
The GoogleScraper.search() methos returns a list of special tuples! Each of these tuples represents a URL.

History
=======
This was originally posted at the following blog http://incolumitas.com/2013/01/06/googlesearch-a-rapid-python-class-to-get-search-results/


USAGE
=====

import GoogleScraper
import urllib.parse

if __name__ == '__main__':
	
	urls = GoogleScraper.scrape('hochwasserhose', number_pages=2)
	for url in urls:
		# You can access all parts of the search results like that
		# url.scheme => URL scheme specifier (Ex: 'http')
		# url.netloc => Network location part (Ex: 'www.python.org')
		# url.path => URL scheme specifier (Ex: ''help/Python.html'')
		# url.params => Parameters for last path element
		# url.query => Query component
		print(urllib.parse.unquote(url.geturl()))

	print('#################################################################')	
	print('[!] Received %d results by asking %d pages with %d results per page' %
				(len(urls), 2, 100))
