---
layout: post
title:      "Rspec and Test Driven Development"
date:       2019-12-04 07:19:52 +0000
permalink:  rspec_and_test_driven_development
---


Writing tests are fun. They make your app doubly satisfying to see all the tests pass and show in green.
Taking the time to write your tests first can help you to think through what you want to accomplish before you actually do it.

Go ahead and do yourself a favor and set up your project with some rspec. You can use the gem:


*gem 'rspec ',  '~> 3.0'*

and run

*budle install*


Now your tests will live in a spec file or directory and use a simple language to set a test. Something like:

spec/testy_test_spec.rb


Inside your test file you will need to require the file that contains the code you would like to test.

```
require_relative '../file_to_test.rb'

describe "a_method_to_test" do
  it "returns_what_i_want" do

    expect(what_i_want).to eq("pizza")
  end
end
```


All in all super easy but super handy when devloping on a team or when you want to grow your code base.







