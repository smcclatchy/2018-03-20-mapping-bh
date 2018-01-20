---
layout: workshop      # DON'T CHANGE THIS.
carpentry: ""    # what kind of Carpentry (must be either "lc" or "dc" or "swc")
venue: "The Jackson Laboratory"
address: "Bioinformatics Training Room, 600 Main Street, Bar Harbor, Maine"
country: "us"
language: "en"
latlng: "44.365994,-68.196389"
humandate: "Mar 20-21, 2018"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:00 am - 5:00 pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2018-03-20    
enddate: 2018-03-21
instructor: ["Sue McClatchy", "Dan Gatti"]
helper: ["TBD"]
email: ["susan.mcclatchy@jax.org"]
collaborative_notes:             # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite: 42370776132          # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'bin/workshop_check.py' *before* committing to make sure that changes are good.
{% endcomment %}

{% comment %}
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="248px"
  scrolling="auto">
</iframe>
{% endif %}

<h2 id="general">General Information</h2>

{% comment %}
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/intro.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/intro.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/intro.html %}
{% endif %}

{% comment %}
  AUDIENCE

  Explain who your audience is.  (In particular, tell readers if the
  workshop is only open to people from a particular institution.
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/who.html %}
{% endif %}

{% comment %}
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use http://itouchmap.com/latlong.html to find the lat/long of an
  address.
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
  JAX employees can locate the bioinformatics training room in building 1, unit 5 on
  this <a href="https://myjax-p.jax.org/Facilities/engineering/GeneralMap/rl_locator_map.pdf">campus map</a>.
</p>
{% endif %}

{% comment %}
  DATE

  This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges
  on. They should have a few specific software packages installed (listed
  <a href="#setup">below</a>). They are also required to abide by
  {% if page.carpentry == "swc" %}
  Software Carpentry's
  {% elsif page.carpentry == "dc" %}
  Data Carpentry's
  {% elsif page.carpentry == "lc" %}
  Library Carpentry's
  {% endif %}
  <a href="{{site.swc_site}}/conduct.html">Code of Conduct</a>.
</p>

{% comment %}
  ACCESSIBILITY

  Modify the block below if there are any barriers to accessibility or
  special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organisers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
</p>

{% comment %}
  CONTACT EMAIL ADDRESS

  Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
    {% for email in page.email %}
      {% if forloop.last and page.email.size > 1 %}
        or
      {% else %}
        {% unless forloop.first %}
        ,
        {% endunless %}
      {% endif %}
      <a href='mailto:{{email}}'>{{email}}</a>
    {% endfor %}
  {% else %}
    to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

{% comment %}
  SCHEDULE

<h2 id="schedule">Schedule</h2>

<div class="row">
    <div class="col-md-6">
        <h3>Tuesday, March 20</h3>
            <table class="table table-striped">
                <tr> <td>09:00</td>  <td><a href="{{site.swc_pages}}/01-introduction/">Introduction</a></td> </tr>
                <tr> <td>09:15</td>  <td><a href="{{site.swc_pages}}/02-input-file-format/">Input File Format</a></td> </tr>
                <tr> <td>09:30</td>  <td><a href="{{site.swc_pages}}/03-calc-genoprob/">Calculating Genotype Probabilities</a></td> </tr>
                <tr> <td>10:00</td>  <td><a href="{{site.swc_pages}}/04-calc-kinship/">Calculating A Kinship Matrix</a></td> </tr>
                <tr> <td>10:45</td>  <td>Coffee</td> </tr>
                <tr> <td>11:00</td>  <td><a href="{{site.swc_pages}}/05-special-x-covar/">Special covariates for the X chromosome</a></td> </tr>
                <tr> <td>11:15</td>  <td><a href="{{site.swc_pages}}/06-perform-genome-scan/">Performing a genome scan</a></td> </tr>
                <tr> <td>12:00</td>  <td>Lunch break</td> </tr>
                <tr> <td>13:00</td>  <td><a href="{{site.swc_pages}}/07-find-lod-peaks/">Finding LOD peaks</a></td> </tr>
                <tr> <td>13:30</td>  <td><a href="{{site.swc_pages}}/08-perform-genome-scan-lmm/">Performing a genome scan with a linear mixed model</a></td> </tr>
                <tr> <td>14:00</td>  <td><a href="{{site.swc_pages}}/09-perform-genome-scan-bin/">Performing a genome scan with binary traits</a></td> </tr>
               <tr> <td>14:30</td>  <td>Coffee</td> </tr>
               <tr> <td>14:45</td>  <td><a href="{{site.swc_pages}}/10-perform-perm-test/">Performing a permutation test</a></td> </tr>
               <tr> <td>15:30</td>  <td><a href="{{site.swc_pages}}/11-est-qtl-effects/">Estimated QTL effects</a></td> </tr>
               <tr> <td>16:00</td>  <td><a href="{{site.swc_pages}}/12-snp-assoc/">SNP association</a></td> </tr>
                <tr> <td>16:45</td>  <td>Wrap-up</td> </tr>
            </table>
        </div>
        <div class="col-md-6">
            <h3>Wednesday, March 21</h3>
                <table class="table table-striped">
                    <tr> <td>09:00</td>  <td><a href="{{site.swc_pages}}/13-qtl-in-do/">QTL analysis in Diversity Outbred Mice</a></td> </tr>
                    <tr> <td>11:45</td>  <td>Wrap-up</td> </tr>
                    <tr> <td>12:00</td>  <td>End</td> </tr>
                </table>
            </div>
        </div>


{% if page.carpentry == "swc" %}
  {% include sc/schedule.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/schedule.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/schedule.html %}
{% endif %}

{% comment %}
  Collaborative Notes

  If you want to use an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<hr/>

{% comment %}
  SYLLABUS

  Show what topics will be covered.

  1. If your workshop is R rather than Python, remove the comment
     around that section and put a comment around the Python section.
  2. Some workshops will delete SQL.
  3. Please make sure the list of topics is synchronized with what you
     intend to teach.
  4. You may need to move the div's with class="col-md-6" around inside
     the div's with class="row" to balance the multi-column layout.

  This is one of the places where people frequently make mistakes, so
  please preview your site before committing, and make sure to run
  'tools/check' as well.
{% endcomment %}
<h2 id="syllabus">Syllabus</h2>

{% if page.carpentry == "swc" %}
  {% include sc/syllabus.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/syllabus.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/syllabus.html %}
{% endif %}

<hr/>

{% comment %}
  SETUP

  Delete irrelevant sections from the setup instructions.  Each
  section is inside a 'div' without any classes to make the beginning
  and end easier to find.

  This is the other place where people frequently make mistakes, so
  please preview your site before committing, and make sure to run
  'tools/check' as well.
{% endcomment %}

<h2 id="setup">Setup</h2>

<p>
  To participate in a
  {% if page.carpentry == "swc" %}
  Software Carpentry
  {% elsif page.carpentry == "dc" %}
  Data Carpentry
  {% elsif page.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  workshop,
  you will need access to the software described below.
  In addition, you will need an up-to-date web browser.
</p>
<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>

<div id="r"> <!-- Start of 'R' section. -->
<h3>R</h3>

<p>
<a href="http://www.r-project.org">R</a> is a programming language
that is especially powerful for data exploration, visualization, and
statistical analysis. To interact with R, we use
<a href="http://www.rstudio.com/">RStudio</a>.
</p>

<div class="row">
<div class="col-md-4">
<h4 id="r-windows">Windows</h4>
<a href="https://www.youtube.com/watch?v=q0PjTAylwoU">Video Tutorial</a>
<p>
Install R by downloading and running
<a href="http://cran.r-project.org/bin/windows/base/release.htm">this .exe file</a>
from <a href="http://cran.r-project.org/index.html">CRAN</a>.
Also, please install the
<a href="http://www.rstudio.com/ide/download/desktop">RStudio IDE</a>.
Note that if you have separate user and admin accounts, you should run the
installers as administrator (right-click on .exe file and select "Run as
administrator" instead of double-clicking). Otherwise problems may occur later,
for example when installing R packages.
</p>
</div>
<div class="col-md-4">
<h4 id="r-macosx">Mac OS X</h4>
<a href="https://www.youtube.com/watch?v=5-ly3kyxwEg">Video Tutorial</a>
<p>
Install R by downloading and running
<a href="http://cran.r-project.org/bin/macosx/R-latest.pkg">this .pkg file</a>
from <a href="http://cran.r-project.org/index.html">CRAN</a>.
Also, please install the
<a href="http://www.rstudio.com/ide/download/desktop">RStudio IDE</a>.
</p>
</div>
<div class="col-md-4">
<h4 id="r-linux">Linux</h4>
<p>
You can download the binary files for your distribution
from <a href="http://cran.r-project.org/index.html">CRAN</a>. Or
you can use your package manager (e.g. for Debian/Ubuntu
run <code>sudo apt-get install r-base</code> and for Fedora run
<code>sudo dnf install R</code>).  Also, please install the
<a href="http://www.rstudio.com/ide/download/desktop">RStudio IDE</a>.
</p>
</div>
</div>
</div> <!-- End of 'R' section. -->

