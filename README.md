# How to use Jekyll for GitHub pages

This manual is based on the installation manual on the [Jekyll](https://jekyllrb.com) website and the blog [Jens Willmer](http://jwillmer.de/blog/tutorial/how-to-install-jekyll-and-pages-gem-on-windows-10-x46) written by Jens Willmer.

Officially Jekyll is not supported on Windows but it works anyway.

0. Install GitHub Desktop
1. Install Ruby (http://rubyinstaller.org/downloads/, I used version 2.0.0-p648 (x64), add Ruby to your path variable)
2. Install Jekyll (enter gem install jekyll in command prompt)
3. Install and configure Ruby Development Kit (I used version DevKit-mingw64-64-4.7.2-20130224-1432-sfx)
3.1. Open command prompt in C:\DevPrograms\devkit
3.2. Execute ruby dk.rb init to create a file called config.yml
3.3. Edit the config.yml file and include the path to Ruby - C:/DevPrograms/Ruby200-x64 (I my case it was already set)
3.4. Execute the following command to set the path: ruby dk.rb install
4. Install Bundler package (enter gem install bundler in command prompt)

5. Clone gh-pages branch
	5.1 enter git clone https://github.com/marinusgeuze/developerquest.git in command prompt)
	5.2 cd developerquest
	5.3 git checkout --orphan gh-pages
	5.4 git rm -rf .
6. Create Jekyll website
	jekyll new .
7. Install and configure github-gem
7.1 Create a file called Gemfile without any extension in your root directory of your blog
7.2 Copy & past the two lines into the file:
	source 'http://rubygems.org'
	gem 'github-pages'
7.3 Open a command prompt in your root directory
7.4 Install github-pages: bundle install
8. Start development server which allows you to preview your content (enter bundle exec jekyll serve in command prompt).
9. Watch your site on http://localhost:4000/
10. Change whatever you want
11. Change the _config.yml file
	baseurl: "/developerquest" 
	url: "https://github.com/marinusgeuze" 

	NOTE: For local development your baseurl property in _config.yml must be empty

12. Add a .gitignore file with ignores for: _site .sass-cache .jekyll-metadata
9. Commit your site to GitHub pages
	git add .
	git commit -a -m "First pages commit"
	git push origin gh-pages

10. Watch your new site on http://marinusgeuze.github.io/developerquest