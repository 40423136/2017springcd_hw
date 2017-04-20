# Liquid-style Tags
*Author: Jake Vanderplas <jakevdp@cs.washington.edu>*
 
This plugin allows liquid-style tags to be inserted into markdown within
Pelican documents. Liquid uses tags bounded by ``{{% ... %}}``, and is used
to extend markdown in other blogging platforms such as octopress.
 
This set of extensions does not actually interface with liquid, but allows
users to define their own liquid-style tags which will be inserted into
the markdown preprocessor stream.  There are several built-in tags, which
can be added as follows.
 
First, in your pelicanconf.py file, add the plugins you want to  use:
 
    PLUGIN_PATH = '/path/to/pelican-plugins'
    PLUGINS = ['liquid_tags.img', 'liquid_tags.video',
               'liquid_tags.youtube', 'liquid_tags.vimeo',
               'liquid_tags.include_code', 'liquid_tags.notebook']
 
There are several options available
 
## Image Tag
To insert a sized and labeled image in your document, enable the
``liquid_tags.img`` plugin and use the following:
 
    {{% img [class name(s)] path/to/image [width [height]] [title text | "title text" ["alt text"]] %}}
 
### Base64 Image (inline image) tag
 
There is one more tag for image: ``b64img``. It is based on ``img`` tag, but instead of inserting link on image it acutally reads image and inserts it as base64 text into ``<img src="``" attribute.="" to="" use="" it:="" 1.="" enable="" ``liquid_tags.b64img``="" insert="" tag="" as="" you'd="" image="" one:="" ``{{%="" b64img="" [class="" name(s)]="" path="" [width="" [height]]="" [title="" text="" |="" "title="" text"="" ["alt="" text"]]="" %}}``="" images="" are="" read="" on="" compilation="" phase="" so="" you="" can="" any="" local="" (just="" be="" sure="" that="" will="" remain="" there="" next="" compilation)="" ##="" instagram="" a="" sized="" and="" labeled="" in="" your="" document="" by="" its="" shortcode="" (such="" ``pfi0caizna``),="" the="" ``liquid_tags.gram``="" plugin="" following:="" {{%="" gram="" [size]="" [width]="" %}}="" specify="" size="" with="" `t`,="" `m`,="" or="" `l`.="" flickr="" post,="" follow="" these="" steps:="" ``liquid_tags.flickr``="" 2.="" [get="" an="" api="" key="" from="" flickr](https:="" www.flickr.com="" services="" apps="" create="" apply)="" 3.="" add="" flickr_api_key="" config="" 4.="" this="" document:="" image_id="" [small|medium|large]="" text"|'alt="" text']="" giphy="" gif="" id="" ``amsjfs6ofx0fc``),="" ``liquid_tags.giphy``="" gif_id="" important:="" have="" request="" production="" [here](https:="" api.giphy.com="" submit).="" for="" first="" runs="" could="" also="" public="" beta="" get="" github.com="" giphyapi).="" soundcloud="" widget="" ``liquid_tags.soundcloud``="" track_url="" youtube="" video="" into="" ``liquid_tags.youtube``="" plugin,="" youtube_id="" [height]="" width="" height="" pixels,="" optionally="" specified.="" if="" they="" not,="" then="" dimensions="" 640="" (wide)="" 390="" (tall).="" you're="" experiencing="" issues="" code="" generating="" (i.e.="" missing="" closing="" tags),="" `summary_max_length="None`" config.="" vimeo="" ``liquid_tags.vimeo``="" vimeo_id="" flash="" html5-friendly="" ``liquid_tags.video``="" url="" video.mp4="" [="" poster.png]="" original="" used.="" poster="" is="" which="" used="" preview="" of="" video.="" file,="" make="" it's="" static="" directory="" put="" appropriate="" url.="" audio="" html5="" ``liquid_tags.audio``="" [url="" audio]="" up="" 3="" urls="" possible.="" different="" versions="" file="" want="" post="" because="" not="" every="" browser="" support="" format.="" include="" link="" ``liquid_tags.include_code``="" include_code="" code.py="" [lang:python]="" [lines:x-y]="" [:hidefilename:]="" [title]="" all="" arguments="" optional="" but="" their="" order="" must="" kept.="" `:hidefilename:`="" only="" allowed="" title="" given.="" lines:1-10="" :hidefilename:="" test="" example="" show="" 10="" lines="" while="" hiding="" actual="" filename.="" script="" ``code``="" subdirectory="" content="" folder:="" default="" location="" changed="" specifying="" code_dir="code" within="" configuration="" file.="" additionally,="" resulting="" hyperlink="" work,="" listed="" under="" static_paths="" setting,="" e.g.:="" 'code']="" ipython="" notebooks="" [ipython][]="" notebook="" ``liquid_tags.notebook``="" filename.ipynb="" should="" specified="" relative="" ``notebooks``="" directory.="" optionally,="" file:="" notebook_dir="notebooks" conversion="" rendering="" rather="" involved,="" few="" extra="" steps="" required="" plugin:="" -="" first,="" need="" install="" ipython:="" pip="" after="" typing="" "make="" html"="" when="" using="" tag,="" called="" ``_nb_header.html``="" produced="" main="" included="" header="" theme.="" easy="" way="" accomplish="" following="" template="" theme="" use:="" extra_header="" {{="" }}="" endif="" line:="" proper="" css="" formatting="" document.="" ###="" tags="" has="" two="" arguments:="" ``cells``="" ``language``.="" slice="" cells="" include:="" cells[2:8]="" name="" language="" pygments="" highlighting="" cells.="" list="" short="" names="" languages="" highlight="" found="" [here](http:="" www.pygments.org="" docs="" lexers="" ).="" language[julia]="" may="" helpful="" those="" [ijulia](https:="" julialang="" ijulia.jl)="" other="" language,="" especially="" project="" [broadens="" scope](https:="" wiki="" roadmap:-ipython)="" [language="" compatibility](http:="" jupyter.org="" default,="" ``ipython``.="" options="" separately,="" together,="" at="" all.="" however,="" both="" come="" before="" ``language``:="" collapsible="" enables="" input="" boxes.="" work="" copy="" ``pelicanhtml_3.tpl``="" (for="" 3.x,="" ``pelicanhtml_2.tpl``="" 2.x)...)="" top="" level="" pelican="" blog.="" containing="" comment="" line="" ``#="" <!--="" collapse="True" --="">`` will be collapsed when the html page is
loaded and can be expanded by clicking on them. Cells containing the
comment line ``# <!-- collapse=False -->`` will be open on load but
can be collapsed by clicking on their header. Cells without collapse
comments are rendered as standard code input cells.
 
## Testing
 
To test the plugin in multiple environments we use [tox](http://tox.readthedocs.org/en/latest/), to run the entire test suite, just type:
 
 
wzxhzdk:0
 
 
[IPython]: http://ipython.org/
</jakevdp@cs.washington.edu>