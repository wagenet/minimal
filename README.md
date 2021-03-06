# Minimal::Template [![Build Status](https://secure.travis-ci.org/svenfuchs/minimal.png?branch=master)](http://travis-ci.org/svenfuchs/minimal)

Minimal::Template is an experimental, minimalistic templating engine inspired by
[Markaby]:(http://github.com/markaby/markaby) &
[Erector]:(http://erector.rubyforge.org) but much smaller (~55 loc) and
targeted at Rails 3.

    # views/foo/bar.rb
    module Foo
      class Bar < Minimal::Template
        def to_html
          html do
            head
            body do
              h1 'plain'
              p  local
            end
          end
        end
      end
    end

    # somewhere else
    view = ActionView::Base.new('path/to/your/views')
    view.render(:file => 'foo/bar', :locals => { :local => 'local' })

    # => '<html><head></head><body><h1>plain</h1><p>local</p></body></html>'</pre>

