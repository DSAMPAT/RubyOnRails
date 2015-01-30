# RubyOnRails

From http://railsapps.github.io/installrubyonrails-mac.html

Install Ruby on Rails · Mac OS X Yosemite
by Daniel Kehoe
Last updated 22 December 2014

Install Ruby on Rails 4.2 on Mac OS X Yosemite. Up-to-date, detailed instructions for the Rails newest release. How to install Rails 4.2, the newest version of Rails, on Mac OS X 10.10 Yosemite.

This in-depth installation guide is used by professional developers to configure their working environment for real-world Rails development.

These instructions can be used for Mac OS X 10.9 Mavericks. Installing Ruby on Rails on Mavericks is the same, but you should upgrade from Mavericks to Yosemite if you can.

For an overview of what’s changed in each Rails release, see a Ruby on Rails Release History.

If You Are New to Rails
To use Rails on Mac OS X, you’ll need Ruby (an interpreter for the Ruby programming language) plus gems (software libraries) containing the Rails web application development framework. If you’re new to Rails, see What is Ruby on Rails?, the book Learn Ruby on Rails, and recommendations for a Rails tutorial.

Join RailsApps
What is the RailsApps Project?
This is an article from the RailsApps project. The RailsApps project provides example applications that developers use as starter apps. Hundreds of developers use the apps, report problems as they arise, and propose solutions. Rails changes frequently; each application is known to work and serves as your personal “reference implementation.” Support for the project comes from subscribers. If this article is useful, please support us and join the RailsApps project.

Ruby on Rails for Mac OS X Yosemite
Mac OS X comes with a “system Ruby” pre-installed. Mac OS X Yosemite includes Ruby 2.0.0p481 which is not the newest version. You should update to Ruby 2.2.0 by using RVM, the Ruby Version Manager.

If you are maintaining older Rails applications, you will likely need to install Ruby 1.9.3. And in the future, you will need to install newer Ruby versions as they are released. Even if you are a student only building new Rails applications, you should be prepared to manage multiple versions of Ruby. These are all reasons to use a Ruby version manager such as RVM.

If You Updated to Mac OS X Yosemite
If you updated to Yosemite from an earlier version of Mac OS X, and you previously installed a Rails development environment, your earlier installation remains intact. You will need to install the new version of Xcode Command Line Tools (full instructions below). Though Rails is still intact after an update, read through this article and take this opportunity to update your development environment.

Updating Ruby on Rails
If you have an older version of Rails installed on your Mac, and you wish to upgrade to a newer version of Rails, see the article Updating Rails.

Use a Ruby Version Manager
You’ll need an easy way to switch between Ruby versions. Just as important, you’ll have a dependency mess if you install gems into the system environment. I recommend RVM to manage Ruby versions and gems because it is popular, well-supported, and full-featured. If you are an experienced Unix administrator, you can consider alternatives such as Chruby or Sam Stephenson’s rbenv. Conveniently, you can use RVM to install Ruby.

Don’t Use a One-Click Installer
You may hear about one-click installation programs such as RailsInstaller, Cinderella, and BitNami RubyStack. These installation programs are often outdated and they are no longer needed as RVM will set up almost everything needed to install Ruby. In particular, I don’t recommend RailsInstaller for experienced developers as it installs RVM at the system level creating potential conflicts.

A Hosted Development Alternative
You can use Ruby on Rails without actually installing it on your computer. Hosted development, using a service such as Nitrous.io, means you get a computer “in the cloud” that you use from your web browser. Any computer can access the hosted development environment, though you’ll need a broadband connection. Nitrous.io is free for small projects.

Using a hosted environment means you are no longer dependent on the physical presence of a computer that stores all your files. If your computer crashes or is stolen, you can continue to use your hosted environment from any other computer. Likewise, if you frequently work on more than one computer, a hosted environment eliminates the difficulty of maintaining duplicate development environments. For these reasons some developers prefer to “work in the cloud” using Nitrous.io. For more on Nitrous.io, see the article Ruby on Rails with Nitrous.io. Nitrous.io is a good option if you have trouble installing Ruby on Rails on your Mac.

Prepare Your Computer
You’ll need to prepare your computer before installing Ruby on Rails.

Upgrade Mac OS X to 10.10
Mac OS X Yosemite was released on October 16, 2014. Make sure you have the latest version of Mac OS X. Under the Apple menu, check “About This Mac.” It should show “Version 10.10” or newer. If you’ve owned your Mac for several years and haven’t updated Mac OS X, be prepared to spend several hours updating the operating system.

If you need to upgrade, see Apple’s instructions How to upgrade to OS X Yosemite. You can install Mac OS X 10.10 (Yosemite) from the Mac App Store for free. Allow plenty of time for the download and installation (it may take several hours).

Terminal Application
You’ll need to use the Terminal application to install Ruby and develop Rails applications. The Terminal application or console gives us access to the Unix command line, or shell. We call the command line the shell because it is the outer layer of the operating system’s internal mechanisms (which we call the kernel). Find the Mac OS X Terminal application by using the Command-Spacebar combination and searching for “Terminal.” It’s in the Applications/Utilities/ folder.

Try out the terminal application by entering a shell command:

$ whoami
Don’t type the $ character. The $ character is a cue that you should enter a shell command. This is a longtime convention that indicates you should enter a command in the terminal application. The Unix shell command whoami returns your username.

To learn more about Unix shell commands, read The Command Line Crash Course.

Is Xcode Already Installed?
You don’t need the full Xcode package to get the Xcode Command Line Tools. You only need the full Xcode package if you are doing development of applications for the Apple operating systems. However, you may have previously installed the full Xcode package.

Check if the full Xcode package is already installed:

$ xcode-select -p
If you see:

/Applications/Xcode.app/Contents/Developer
the full Xcode package is already installed.

You will need to update Xcode to the newest version (Xcode 6 or newer). Go to the App Store application and check “Updates.” After updating Xcode, be sure to launch the Xcode application and accept the Apple license terms.

If you see a file location that contains spaces in the path:

/Applications/Apple Dev Tools/Xcode.app/Contents/Developer
you must delete Xcode. RVM cannot accommodate spaces in a path so RVM will fail when you attempt to install Ruby. You can either install only the Xcode Command Line Tools (instructions below) or reinstall the full Xcode package.

Install Xcode Command Line Tools
Before installing Ruby, you’ll need to prepare your computer by installing Apple’s Xcode Command Line Tools.

The Xcode Command Line Tools provide a C language compiler needed to install Ruby. For many Rails projects, you will need the C language compiler to install gems that use native extensions.

Mac OS X Yosemite will alert you when you enter a command in the terminal that requires Xcode Command Line Tools. For example, you can enter gcc, git, or make.

Try it. Enter:

$ gcc
You’ll see an alert box:

alert Xcode Command Line Tools is required

Alternatively, you can use a command to install Xcode Command Line Tools. It will produce a similar alert box. Note the double hyphen:

$ xcode-select --install
Click “Install” to download and install Xcode Command Line Tools.

The instructions in the alert box are confusing. You don’t need to “Get Xcode” from the App Store. Just click “Install” for the Xcode Command Line Tools.

downloading Xcode Command Line Tools

installed Xcode Command Line Tools

Verify that you’ve successfully installed Xcode Command Line Tools:

$ xcode-select -p
/Library/Developer/CommandLineTools
Just to be certain, verify that gcc is installed:

$ gcc --version
Configured with: --prefix=/Library/Developer/CommandLineTools/usr --with-gxx-include-dir=/usr/include/c++/4.2.1
Apple LLVM version 6.0 (clang-600.0.54) (based on LLVM 3.5svn)
Target: x86_64-apple-darwin14.0.0
Thread model: posix
On earlier versions of Mac OS X, it was more difficult to install Xcode Command Line Tools. It required a huge download of the full Xcode package from the Mac App Store or registration as an Apple developer for a smaller Command Line Tools package. Mac OS X 10.9 Mavericks made installation of Xcode Command Line Tools much simpler.

Alternatives
The OSX GCC Installer is an open source project to provide the GCC compiler and related tools. In a recent blog post, Xcode, GCC, and Homebrew, the project maintainer recommends installing the Xcode Command Line Tools because the open source project is unable to duplicate the complete Apple package (notably, the Node software project isn’t supported).

Configure Git
Before installing Ruby on Rails, you should configure Git. Git is automatically installed as part of the Xcode Command Line Tools. Or, if you updated from a previous version of Mac OS X, you may have installed Git previously.

Git provides a source control repository. Developers use Git to roll back code changes as needed, to collaborate with others, and deploy applications for hosting with a service such as Heroku. As a Rails developer, you’ll use Git with a GitHub account for remote backup and collaboration. See the article Rails with Git and GitHub for more background.

Check that Git is installed:

$ git version
git version 1.9.3 (Apple Git-50)
Configure Git if you haven’t used it before. First, list the current settings with the git config -l --global command. Then set user.name and user.email if necessary:

$ git config -l --global
fatal: unable to read config file '/Users/.../.gitconfig': No such file or directory
$ git config --global user.name "Your Real Name"
$ git config --global user.email me@example.com
$ git config -l --global
user.name=Your Real Name
user.email=me@example.com
Now you’ll be ready to use Git when you need it.

Install Ruby Using RVM
Use RVM, the Ruby Version Manager, to install Ruby and manage your Rails versions.

RVM will leave your “system Ruby” untouched and use your shell to intercept any calls to Ruby. There’s no need to remove it. The “system Ruby” will remain on your system and the RVM version will take precedence.

Ruby 2.2.0 was current when this was written. You can check for the current recommended version of Ruby. RVM will install the newest stable Ruby version.

The RVM website explains how to install RVM. Here’s the simplest way:

$ \curl -L https://get.rvm.io | bash -s stable --ruby
Note the backslash before “curl” (this avoids potential version conflicts).

The “—ruby” flag will install the newest version of Ruby.

RVM includes an “autolibs” option to identify and install components needed for your operating system. See the article RVM Autolibs: Automatic Dependency Handling and Ruby 2.0 for more information.

On a new, clean version of Mac OS X, RVM will check requirements and install MacPorts (you may need to enter your user password). RVM will update your system and install dependencies required for installing Ruby on Mac OS X. You may be prompted to install a Java SE 6 runtime (for the javac Java compiler).

If your Mac user name contains a space character, you must change you account name to remove the space.

If You Already Have RVM Installed
If you already have RVM installed, update it to the latest version and install Ruby:

$ rvm get stable --autolibs=enable
$ rvm install ruby
$ rvm --default use ruby-2.2.0
RVM Troubleshooting
You can use rvm implode to remove all traces of RVM from your system.

If you have trouble installing Ruby with RVM, you can get help directly from the RVM team using the IRC (Internet Relay Chat) channel #rvm on irc.freenode.net:

http://webchat.freenode.net/?channels=rvm

If you’ve never used IRC, it’s worthwhile to figure out how to use IRC because the RVM team is helpful and friendly. IRC on freenode requires registration (see how to register).

Check the Gem Manager
RubyGems is the gem manager in Ruby.

Check the installed gem manager version. You may see:

$ gem -v
2.2.2
At the time this was written, a newer RubyGems version was available. Use gem update --system to upgrade the Ruby gem manager:

$ gem update --system
RVM Gemsets
Not all Rails developers use RVM to manage gems, but many recommend it.

Display a list of gemsets:

$ rvm gemset list

gemsets for ruby-2.2.0
=> (default)
   global
Only the “default” and “global” gemsets are pre-installed.

If you get an error “rvm is not a function,” close your console and open it again.

RVM’s Global Gemset
See what gems are installed in the “global” gemset:

$ rvm gemset use global
$ gem list
A trouble-free development environment requires the newest versions of the default gems.

Several gems are installed with Ruby or the RVM default gemset:

bundler
bundler-unload
rake
rubygems-bundler
rvm
To get a list of gems that are outdated:

$ gem outdated
### list not shown for brevity
To update all stale gems:

$ gem update
### list not shown for brevity
In particular, rake should be updated to version 10.2.1 or newer.

Stay Current
You can track updates to gems at the RubyGems.org site by creating an account and visiting your dashboard. Search for each gem you use and “subscribe” to see a feed of updates in the dashboard (an RSS feed is available from the dashboard). After you’ve built an application and set up a GitHub repository, you can stay informed with Gemnasium or VersionEye. These services survey your GitHub repo and send email notifications when gem versions change. Gemnasium and VersionEye are free for public repositories with a premium plan for private repositories.

Faster Gem Installation
By default, when you install gems, documentation files will be installed. Developers seldom use gem documentation files (they’ll browse the web instead). Installing gem documentation files takes time, so many developers like to toggle the default so no documentation is installed.

Here’s how to speed up gem installation by disabling the documentation step:

$ echo "gem: --no-document" >> ~/.gemrc
This adds the line gem: --no-document to the hidden .gemrc file in your home directory.

Nokogiri
Nokogiri is a gem that is a dependency for many other gems. Nokogiri is a gem that requires compilation for your specific operating system. As such, if your system environment doesn’t match Nokogiri’s requirements, compilation of Nokogiri will fail. If your system is configured properly, you’ll be able to compile Nokogiri. However, compilation takes time. Every time you install the Nokogiri gem, you’ll wait (as long as five minutes).

To save time, install the Nokogiri gem in the RVM global gemset:

$ gem install nokogiri
During installation, Nokogiri will display two lengthy messages in the console. It will also pause without displaying any progress for as long as five minutes. Don’t assume installation has failed unless you see an error message or you’ve waited more than ten minutes.

If installation fails, make sure your system is configured properly (look for help on Stack Overflow).

Rails Installation Options
Check for the current version of Rails. Rails 4.2.0 was current when this was written.

You can install Rails directly into the global gemset. However, many developers prefer to keep the global gemset sparse and install Rails into project-specific gemsets, so each project has the appropriate version of Rails.

If you install Rails at this point, you will install it into the global gemset.

Instead, make a gemset just for the current stable release:

$ rvm use ruby-2.2.0@rails4.2 --create
Here are the options you have for installing Rails.

If you want the most recent stable release:

$ gem install rails
$ rails -v
If you want the newest beta version or release candidate, you can install with --pre.

$ gem install rails --pre
$ rails -v
Or you can get a specific version.

For example, if you want the Rails 3.2.18 release:

$ gem install rails --version=3.2.18
$ rails -v
Create a Workspace Folder
You’ll need a convenient folder to store your Rails projects. You can give it any name, such as code/ or projects/. For this tutorial, we’ll call it workspace/.

Create a projects folder and move into the folder:

$ mkdir workspace
$ cd workspace
This is where you’ll create your Rails applications.

New Rails Application
Here’s how to create a project-specific gemset, installing Rails, and creating a new application.

$ mkdir myapp
$ cd myapp
$ rvm use ruby-2.2.0@myapp --ruby-version --create
$ gem install rails
$ rails new .
We’ll name the new application “myapp.” Obviously, you can give it any name you like.

With this workflow, you’ll first create a root directory for your application, then move into the new directory.

With one command you’ll create a new project-specific gemset. The option “—ruby-version” creates .ruby-version and .ruby-gemset files in the root directory. RVM recognizes these files in an application’s root directory and loads the required version of Ruby and the correct gemset whenever you enter the directory.

When we create the gemset, it will be empty (though it inherits use of all the gems in the global gemset). We immediately install Rails. The command gem install rails installs the most recent release of Rails.

Finally we run rails new .. We use the Unix “dot” convention to refer to the current directory. This assigns the name of the directory to the new application.

This approach is different from the way most beginners are taught to create a Rails application. Most instructions suggest using rails new myapp to generate a new application and then enter the directory to begin work. Our approach makes it easy to create a project-specific gemset and install Rails before the application is created.

The rails new command generates the default Rails starter app. If you wish, you can use the Rails Composer tool to generate a starter application with a choice of basic features and popular gems.

Quick Test
For a “smoke test” to see if everything runs, display a list of Rake tasks.

$ rake -T
There’s no need to run bundle exec rake instead of rake when you are using RVM (see RVM and bundler integration).

This concludes the instructions for installing Ruby and Rails. Read on for additional advice and tips.

Rails Starter Apps
The starter application you create with rails new is very basic.

Use the Rails Composer tool to build a full-featured Rails starter app.

You’ll get a choice of starter applications with basic features and popular gems.

Here’s how to generate a new Rails application using the Rails Composer tool:

Using the conventional approach:

$ rails new myapp -m https://raw.github.com/RailsApps/rails-composer/master/composer.rb
Or, first creating an empty application root directory:

$ mkdir myapp
$ cd myapp
$ rvm use ruby-2.2.0@myapp --ruby-version --create
$ gem install rails
$ rails new . -m https://raw.github.com/RailsApps/rails-composer/master/composer.rb
The -m option loads an application template that is hosted on GitHub.

You can add the -T flags to skip Test::Unit if you are using RSpec for testing.

You can add the -O flags to skip Active Record if you are using a NoSQL datastore such as MongoDB.

If you get an error “OpenSSL certificate verify failed” when you try to generate a new Rails app, see the article OpenSSL errors and Rails.

Rails Tutorials and Example Applications
The RailsApps project provides example apps that show how real-world Rails applications are built. Each example is known to work and can serve as your personal “reference implementation”. Each is an open source project. Dozens of developers use the apps, report problems as they arise, and propose solutions as GitHub issues. Purchasing a subscription for the tutorials gives the project financial support.

Example Applications for Rails 4.2	Tutorial	Comments
Learn Rails	Learn Ruby on Rails	introduction to Rails for beginners
Rails and Bootstrap	Rails Bootstrap Tutorial	starter app for Rails and Bootstrap
Rails and Foundation	Rails Foundation Tutorial	starter app for Rails and Zurb Foundation
OmniAuth and Rails	OmniAuth Tutorial	OmniAuth for authentication
Devise and Rails	Devise Tutorial	Devise for authentication
Pundit and Rails	Rails Pundit Tutorial	Pundit for authorization
Adding a Gemset to an Existing Application
If you’ve already created an application with the command rails new myapp, you can still create a project-specific gemset. Here’s how to create a gemset for an application named “myapp” and create .ruby-version and .ruby-gemset files in the application’s root directory:

$ rvm use ruby-2.2.0@myapp --ruby-version --create
You’ll need to install Rails and the gems listed in your Gemfile into the new gemset by running:

$ gem install rails
$ bundle install
Specifying a Gemset for an Existing Application
If you have already created both an application and a gemset, but not .ruby-version and .ruby-gemset files, here’s how to add the files. For example, if you want to use an existing gemset named “ruby-2.2.0@myapp”:

$ echo "ruby-2.2.0" > .ruby-version
$ echo "myapp" > .ruby-gemset
Using .ruby-version and .ruby-gemset files means you’ll automatically be using the correct Rails and gem version when you switch to your application root directory on your local machine.

Databases for Rails
Rails uses the SQLite database by default. Mac OS X come with SQLite pre-installed and there’s nothing to configure.

Though SQLite is adequate for development (and even some production applications), a new Rails application can be configured for other databases. The command rails new myapp --database= will show you a list of supported databases.

Supported for preconfiguration are: mysql, oracle, postgresql, sqlite3, frontbase, ibm_db, sqlserver, jdbcmysql, jdbcsqlite3, jdbcpostgresql, jdbc.
PostgreSQL
Use the easy-to-install Max OS X Postgres.app if you’d like to use PostgreSQL.

To create a new Rails application to use PostgreSQL:

$ rails new myapp --database=postgresql
The --database=postgresql parameter will add the pg database adapter gem to the Gemfile and create a suitable config/database.yml file.

Don’t use the --database= argument with the Rails Composer tool. You’ll select a database from a menu instead.

Deployment
If you wish to run your own servers, you can deploy a Rails application using Capistrano deployment scripts. However, unless system administration is a personal passion, it is much easier to deploy your application with a “platform as a service” provider such as Heroku.

Hosting
For easy deployment, use a “platform as a service” provider such as:

Heroku
CloudFoundry
EngineYard
OpenShift
For deployment on Heroku, see the article:

Rails on Heroku
Security
By design, Rails encourages practices that avoid common web application vulnerabilities. The Rails security team actively investigates and patches vulnerabilities. If you use the most current version of Rails, you will be protected from known vulnerabilities. See the Ruby On Rails Security Guide for an overview of potential issues and watch the Ruby on Rails Security Mailing List for announcements and discussion.

Your Application’s Secret Token
Rails uses a session store to provide persistence between page requests. The default session store uses cookies. To prevent decoding of cookie data and hijacking a session, Rails encrypts cookie data using a secret key. When you create a new Rails application using the rails new command, a unique secret key is generated. If you’ve used the Rails Composer tool to generate the application, the application’s secret token will be unique, just as with any Rails application generated with the rails new command.

The file config/secrets.yml contains secret tokens for development and production.

Take care to hide the secret token you use in production. Don’t expose it in a public GitHub repo, or people could change their session information, and potentially access your site without permission. It’s best to set the secret token in a Unix shell variable.

If you need to create a new secret token:

$ rake secret
The command rake secret generates a new random secret you can use. The command won’t install the key; you have to copy the key from the console output to the appropriate file.

Troubleshooting
Problems with RVM
You can get help directly from the RVM team using the IRC (Internet Relay Chat) channel #rvm on irc.freenode.net:

http://webchat.freenode.net/?channels=rvm

If you’ve never used IRC, it’s worthwhile to figure out how to use IRC because the RVM team is helpful and friendly. IRC on freenode requires registration (see how to register).

Problems with “Segmentation Fault”
If you get a “segfault” when you try rails new, try removing and reinstalling RVM. If you are not using the current version of Mac OS X, you should upgrade before installing RVM.

Problems with “Gem::RemoteFetcher::FetchError: SSL_connect”
Ruby and RubyGems (starting with Ruby 1.9.3p194 and RubyGems 1.8.23) require verification of server SSL certificates when Ruby makes an Internet connection via https. If you run rails new and get an error “Gem::RemoteFetcher::FetchError: SSL_connect returned=1 errno=0 state=SSLv3 read server certificate” see this article suggesting solutions: OpenSSL errors and Rails.

Problems with “Certificate Verify Failed”
Are you getting an error “OpenSSL certificate verify failed” when you try to generate a new Rails app from an application template? See this article suggesting solutions: OpenSSL errors and Rails.

Where to Get Help
Your best source for help with problems is Stack Overflow. Your issue may have been encountered and addressed by others.

You can also try Rails Hotline, a free telephone hotline for Rails help staffed by volunteers.

Credits
Daniel Kehoe wrote the article.
