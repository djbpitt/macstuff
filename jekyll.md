# Jekyll and MacOS

The following combination of hints, pulled from assorted sites, enabled me to install Jekyll under Mojave 10.14.5.

1. Update Xcode (App store)
2. Update Xcode command-line tools (`xcode-select --install`)
3. Install (or re-install) headers (`sudo installer -pkg /Library/Developer/CommandLineTools/Packages/macOS_SDK_headers_for_macOS_10.14.pkg -target /`)
4. `brew install ruby`
5. Add `/usr/local/opt/ruby/bin` to the head of your $PATH with ```export PATH=`/usr/local/opt/ruby/bin:$PATH` ```
6. Add `$HOME/.gem/ruby/2.6.0/bin:` to the head of your path (adjust the version number to match your version of ruby, except that the third component should always be `0`)
4. Remove references to Anaconda from your path with ```export PATH=`echo $PATH | sed s/anaconda/ana/g` ```. This is a temporary change, needed only while running the Jekyll installation.
4. Select the correct compiler tools with `sudo xcode-select -s /Library/Developer/CommandLineTools/` (see comment from May 4 by Initgraph at <https://github.com/ffi/ffi/issues/653>).
5. Install Jekyll with `gem install --user-install jekyll`

I am still unable to install ruby versions with `rbenv`. Sigh.