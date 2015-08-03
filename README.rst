dcard_coworker
==============

Dcard crawler using asyncio(coroutine)


Feature
-------
| Get article list and content using coroutine


Packcage Dependency
-------------------
* aiohttp


Example
-------

::

    #!/usr/bin/env python

    import asyncio

    import aiohttp
    import dcard_coworker

    @asyncio.coroutine
    def get_funny_articles():
        session = aiohttp.ClientSession()
        forum_name = 'funny'
        page_index = 1
        result = yield from dcard_coworker.get_articles_of_page(session, forum_name, page_index)
        print(result)

    def main():
        loop = asyncio.get_event_loop()
        loop.run_until_complete(asyncio.wait([get_funny_articles()]))

    if __name__ == '__main__':
        main()


Todo
----
* Add pypi setup
* Add documentation
  

License
-------
(The MIT License)

Copyright (C) 2015 黃健瑋(Chien-Wei Huang)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

