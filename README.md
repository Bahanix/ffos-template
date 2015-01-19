# FFOS app template

Firefox OS open web app template with localisation.

## Note

* To use Rakefile, you will need ruby and bundler: `gem install bundler`
* I advise to swap CACHE and NETWORK in `manifest.appcache` while developping.
* Do not forget to unswap them before building and deploying your app.

## Test with your device or simulator

* Download and install [Firefox Nightly](https://nightly.mozilla.org/)
* Firefox > Developer > WebIDE
* Select your device or simulator
* Open Hosted App
* URL to your `manifest.webapp`
* Run

## With Rakefile

* `rake build` to build your `app.zip`
* `rake deploy` to deploy on Github pages
* `https://bahanix.github.io/ffos-template/`
