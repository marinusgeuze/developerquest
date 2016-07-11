# How to use Jekyll for GitHub pages #

This manual is based on the installation manual on the [Jekyll](https://jekyllrb.com) website and [this blog](http://jwillmer.de/blog/tutorial/how-to-install-jekyll-and-pages-gem-on-windows-10-x46) written by Jens Willmer.

**NOTE:** Officially Jekyll is not supported on Windows but it works anyway.

#### Step by step manual ####

1. Install [Git for Windows](https://git-for-windows.github.io).

2. Install [Ruby](http://rubyinstaller.org/downloads). I used version 2.0.0-p648 (x64) and do not forget to add Ruby to your path variable.

3. Install [Jekyll](https://jekyllrb.com). Command: ```gem install jekyll```

4. Install and configure [Ruby Development Kit](http://rubyinstaller.org/downloads). I used version DevKit-mingw64-64-4.7.2-20130224-1432-sfx.
  * Install the Development Kit in C:\DevPrograms\devkit
  * Open the command prompt in C:\DevPrograms\devkit
  * Execute ```ruby dk.rb init``` to create a file called config.yml
  * Edit the config.yml file and include the path to Ruby - C:/DevPrograms/Ruby200-x64. I my case it was already set.
  * Execute the following command to set the path: ```ruby dk.rb install```

5. Install the Bundler package. Command: ```gem install bundler```

6. Clone the gh-pages branch. Enter these commands:
  * ```git clone https://github.com/marinusgeuze/developerquest.git```
  * ```cd developerquest```
  * ```git checkout --orphan gh-pages```
  * ```git rm -rf .```

7. Create the Jekyll website. Enter command: ```jekyll new .```

8. Install and configure github-gem
  * Create a file called Gemfile without any extension in your root directory of your blog
  * Copy & past these two lines into the file:
   ```source 'http://rubygems.org'```
   ```gem 'github-pages'```
  * Open a command prompt in your root directory of your site
  * Install github-pages. Command: ```bundle install```

9. Start the development server which allows you to preview your content. Command: ```bundle exec jekyll serve```

10. Watch your site on [http://localhost:4000](http://localhost:4000)

11. Change whatever web content you want

12. Change the _config.yml file

	```baseurl: "/developerquest"```

	```url: "https://github.com/marinusgeuze"``` 

	**NOTE:** For local development your baseurl property in the _config.yml must be empty

13. Add a .gitignore file with ignores for: ```_site``` ```.sass-cache``` ```.jekyll-metadata```

14. Commit your site to GitHub pages. Enter these commands:
	* ```git add .```
	* ```git commit -a -m "First pages commit"```
	* ```git push origin gh-pages```

15. Watch your new site on [http://marinusgeuze.github.io/developerquest](http://marinusgeuze.github.io/developerquest)