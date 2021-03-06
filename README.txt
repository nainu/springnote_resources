= Springnote Resources

* Homepage: http://myruby.net/pages/391111
* Author: deepblue (http://myruby.net) and Changshin Lee (http://www.iasandcb.pe.kr)

== DESCRIPTIONS:

ActiveResource wrapper library for Springnote.com's REST API

== REQUIREMENTS:

* activesupport
* activeresource
* oauth
* ruby-hmac

== INSTALL:

* sudo gem install springnote_resources

== How to get keys

1. You need to register your application on Openmaru API Center(https://api.openmaru.com/oauth/new) and 
get the consumer token. Read http://dev.springnote.com/pages/438963 
for more details.

2. Now you need to get the access token for the application you registered.
Read the OAuth tutorial for more details.

3. You have two tokens. Configure SpringnoteResources with the information 
like following code:

Springnote::Base.configuration.set :consumer_token => 'CK', :consumer_secret => 'CS',
  :access_token => 'AK', :access_secret => 'AS',
  :domain => 'notename'

== USAGE:

# Load a page
page = Springnote::Page.find(144)
puts page.source

# Update the page
page = Springnote::Page.find(144)
page.source = '<p>New Contents</p>'
page.save

# Create a new page
page = Springnote::Page.create :title => 'NewName', :source => 'NewContents'

# Destroy the page
Springnote::Page.find(144).destroy

== LICENSE:

(The MIT License)

Copyright (c) 2007 Bryan Kang and Changshin Lee

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
