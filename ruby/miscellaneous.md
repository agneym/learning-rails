# Miscellaneous Notes

## Puts, Print, p, pp

**Puts:**
* Adds an extra newline at the end
* Converts everything to string
* Returns `nil`

**Print**:
* Converts everything to string
* Returns `nil`

**p**:
* Does not convert to string
* Used for debugging
* Returns the object passed to it for printing

**pp**:
* Pretty Print
* Same as `p`

## Falsy 

Only `nil` and `false` are falsy in Ruby. All the other expressions are Truthy.

## String Interpolation

```ruby
name = "Aaron"
puts "Hello, #{name}!"
```

Basically `#` instead of `$` in [template strings](https://hacks.mozilla.org/2015/05/es6-in-depth-template-strings-2/).

Only works with double quotes.

## External Packages

Ruby calls these **gems**. They are centrally hosted at rubygems.org. 

But unlike `npm`, `gem` (like `pip` I guess) installs these dependencies at a global level. You can use a package manager named `bundler` that can manage the dependencies for you at the local project level.

You can install bundler with:

```
gem install bundler
```

Like `package.json`, Ruby has a `Gemfile` which lists the dependencies installed (just that!).

You can install all dependencies in the Gemfile with:

```
bundle install
```

> There is also a Gemfile.lock as in package.lock.json or yarn.lock.

To include a package, require it:

```ruby
require 'digest'
```