
## Introduction

As the CBRAIN system is now open-source, it is time to agree on some
common coding guidelines. Fortunately, Ruby already has a rather strong 
default style that is more or less internationally adopted, unlike many 
other programming languages.

## Table of contents

1. [Commonly acceptable rules](#acceptable_rules)
2. [CBRAIN-specific rules](#CBRAIN_rules)



<a name="acceptable_rules" />
## 1. Commonly acceptable rules

Someone has already written a nice guide. Although it was
written for people developing standalone Ruby applications, many
of the guidelines apply to us too, Rails developers. Read this
document, but skip the sections that only mostly apply to standalone
applications (Benchmarking, Profiling, Unit Testing etc):
[http://www.caliban.org/ruby/rubyguide.shtml](http://www.caliban.org/ruby/rubyguide.shtml)

The most important common style rules are basically:

* Use an indentation of two spaces, like this:

```ruby
class Abc
  def Xyx
    if condition
      do this
    else
      print this
    end
  end
end
```

* Use the Ruby and Rails convention for identifiers:

  - ``SomeClassName``
  - ``def some_method``
  - ``some_variable = "Hi"``

<a name="CBRAIN_rules" />
## 2. CBRAIN-specific rules

The following are our internal rules:

* DO NOT LEAVE TAB CHARACTERS INSIDE THE CODE. You can still use the
  tab key, but make sure that you configure your editor such that the tab
  characters themselves are replaced by normal spaces. All modern
  editors have this option, so figure out how to set this preference
  in your editor. In 'vim', this is done by adding the command "set
  expandtab" in your .vimrc.

* Annotate your classes and methods using the rdoc conventions.
  This will allow you and other programmers to generate nice searchable
  HTML pages for your code by calling the rake commands:

  - ``rake doc:brainportal   (in the BrainPortal subdir)`` --> main index in Brainportal/doc/brainportal/index.html
  - ``rake doc:bourreau      (in the Bourreau subdir)`` --> main index in Bourreau/doc/bourreau/index.html

  Open these with your browser. It may be helpful to bookmark them. Remember
  to regenerate these documents from time to time, whenever the
  code is updated.  An explanation of rdoc is available here:
  [http://rdoc.sourceforge.net/doc/index.html](http://rdoc.sourceforge.net/doc/index.html)
  (Look at the section entitled "Markup").

* Do not write lines that are too long and consistently fold over to
  the other line in your editor. Once in a while it cannot be helped,
  but often it is possible to split long lines into a more elegant
  two line layout. Just be careful WHERE you split it, though,
  as Ruby is particular about interpreting newlines characters as
  statement terminators (unlike Perl and Java and C, which require
  a semicolon). It is best to use a text editor window configured to
  be between 90 and 100 characters wide.

  As examples, assume the following three lines are too long (they
  are not all too long, in fact, it is just an example) and you would like
  to split them a little:

```ruby
  self.addlog("Using Scir for '#{drm}' version '#{version}'")
  raise "Error: file does not exist: #{localpath}" unless File.exists?(localpath)
  providers = self.find(:all, :conditions => { :online => true, :read_only => false })
```

  This could be done this way:

```ruby
  self.addlog("Using Scir for '#{drm}' " +
              "version '#{version}'")
  raise "Error: file does not exist: #{localpath}" unless
      File.exists?(localpath)
  providers = self.find(:all, :conditions =>
                            { :online => true, :read_only => false }
                       )
```

  Note that the continuation line is indented compared to the beginning
  of the statement; the indentation is chosen to be 'pretty'. Also note
  that the 'unless' keyword MUST be left at the end of the first line
  for the second example, otherwise Ruby would execute the ``raise``
  statement unconditionally:

```ruby
  raise "Error: file does not exist: #{localpath}" # WRONG!
    unless File.exists?(localpath)                 # WRONG!
```

**Note**: Original author of this document is Pierre Rioux

