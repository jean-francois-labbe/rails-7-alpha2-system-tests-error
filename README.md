# Rails 7 alpha2 repo to show system tests issue.

**Ruby and ROR versions**
```
$ rails -v => Rails 7.0.0.alpha2
$ ruby -v => ruby 3.0.2p107 (2021-07-07 revision 0db68f0233) [x86_64-linux]
```

**Project setup**
```
$ rails new blog
$ cd blog
$ rails g scaffold post title content:text
$ rails db:migrate
```

**Running tests: ok**
```
$ rails test
Run options: --seed 57086

.......

Finished in 0.453156s, 15.4472 runs/s, 19.8607 assertions/s.
7 runs, 9 assertions, 0 failures, 0 errors, 0 skips
```

**Running system tests: fails**
```
$ rails test:system
Run options: --seed 14447

DEBUGGER: Detaching after fork from parent process 381514
DEBUGGER: Attaching after process 381514 fork to child process 381526
2021-10-15 16:10:55 WARN Selenium [DEPRECATION] [:browser_options] :options as a parameter for driver initialization is deprecated. Use :capabilities with an Array of value capabilities/options if necessary instead.
Capybara starting Puma...
* Version 5.5.2 , codename: Zawgyi
* Min threads: 0, max threads: 4
* Listening on http://127.0.0.1:43629
[Screenshot Image]: /home/jeff/Workspace/freelance/blog/tmp/screenshots/failures_test_should_create_Post.png
E

Error:
PostsTest#test_should_create_Post:
Capybara::ElementNotFound: Unable to find link or button "New Post"
    test/system/posts_test.rb:15:in `block in <class:PostsTest>
```

Check the CI tests https://github.com/jean-francois-labbe/rails-7-alpha2-system-tests-error/runs/3907071991
