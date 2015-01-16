# web-cache-warmer
 
**web-cache-warmer** is a script for warming website and FTP caches. It will download the URL(s) that you specify using the user agent string(s) that you specify. It can also recursively crawl [sitemaps](http://www.sitemaps.org/), and download the URLs contained within them.

See the [**web-cache-warmer** website](http://webcachewarmer.com/) for more documentation.

## Installation

1. Verify that you have [Ruby](https://www.ruby-lang.org/) 1.9.3 (released October 2011) or later installed:

        ruby --version

    Earlier versions may also work, but are untested.

2. Verify that you have [wget](https://www.gnu.org/software/wget/) 1.6 (released December 1999) or later installed:

        wget --version

3. Download and extract the tarball:

        wget https://github.com/mrideout/web-cache-warmer/archive/v0.1.tar.gz
        tar -xzf v0.1.tar.gz
        cd web-cache-warmer-0.1

4. Make **web-cache-warmer** executable:

        chmod 755 web-cache-warmer

5. Optionally, move **web-cache-warmer** into a directory that's in your PATH. For example:

        sudo mv web-cache-warmer /usr/local/bin/
 
## Usage

**web-cache-warmer** *[options]*

| Option                 | Description     
-------------------------|------------------------------------
| -h, --help             | Prints this help message
| -q, --quiet            | Suppress non-error messages
| -s, --sitemap URL      | Space delimited list of XML Sitemap URL(s)
| -u, --url URL          | Space delimited list of URL(s) to download
| -U, --user-agent AGENT | Bar (&#124;) delimited list of user agent(s) to use
| -v, --verbose          | Print verbose output
| -V, --version          | Print version number
| -w, --wget-args ARGS   | Arguments to pass to **wget**. Takes precedence over --user-agent

## Examples

1. Download example.com's home page:

        web-cache-warmer -u http://example.com

2. Recursively download the sitemaps and URLs linked to from example.com's sitemap:

        web-cache-warmer -s http://example.com/sitemap.xml

2. Recursively download the sitemaps and URLs linked to from example.com's sitemap, suppressing non-error messages:

        web-cache-warmer -s http://example.com/sitemap.xml -q

4. Recursively download the sitemaps and URLs linked to from example.com's sitemap using Chrome and Mobile Safari user agents:

        web-cache-warmer -s http://example.com/sitemap.xml -U "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_10_1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/39.0.2171.95 Safari/537.36|Mozilla/5.0 (iPhone; CPU iPhone OS 8_1_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12B440 Safari/600.1.4"
 
## Contributing
 
1. Fork it!

2. Create your feature branch:

        git checkout -b my-new-feature

3. Commit your changes:

        git commit -a -m 'Add some feature'

4. Push to the branch:

        git push origin my-new-feature

5. Submit a pull request.
 
## History

[Matt Rideout](https://www.mattrideout.com/) wrote and released **web-cache-warmer** in January 2015. 
 
## License
 
**web-cache-warmer** is open source software licensed using the 2-class BSD license. See the LICENSE file for details.
