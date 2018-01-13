### pbgnz.github.io
personal web page

#### Slideshow Background:

	This is pretty straightforward, but there are two JS settings you'll want to be aware of
	(found under "Slideshow Background" in assets/js/main.js):

	images

		The list of images to cycle through, given in the following format:

			'url': 'alignment'

		Where 'url' is the image (eg. 'images/foo.jpg', 'http://somewhere.else/foo.jpg'), and
		'alignment' is how the image should be vertically aligned ('top', 'center', or 'bottom').

		Note: Browsers that don't support CSS transitions (like IE<=9) will only see the first image.

	delay

		How long to wait between transitions (in ms). Note that this must be at least twice as long as
		the transition speed itself (currently 3 seconds).


#### Credits:

	Demo Images:
		Unsplash (unsplash.com)

	Icons:
		Font Awesome (fortawesome.github.com/Font-Awesome)

	Other:
		html5shiv.js (@afarkas @jdalton @jon_neal @rem)
		Respond.js (j.mp/respondjs)
            Skel (skel.io) 
    
