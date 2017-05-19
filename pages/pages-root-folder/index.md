---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
widget1:
  title: "About Us"
  url: '/about'
  image: ent015_cropped.jpg
  text: 'Capital Region Otolaryngology Head and Neck Group, LLP has been serving the New York Capital District area for more than 50 years. Our mission is to evaluate each patient by performing comprehensive ear, nose, and throat examinations in order to provide the finest treatment.'
widget2:
  title: "Services"
  url: '/services'
  image: humans/ent173.jpg
  link_list:
    - name: Audiology
      url: services/audiology/
    - name: Otology/Ear Diseases
      url: services/otology/
    - name: Pediatric Otolaryngology
      url: services/pediatric_otolaryngology/
    - name: Sinus
      url: services/sinus/
    - name: Head & Neck Surgery
      url: services/head_neck_surgery/
widget3:
  title: "Locations & Hours"
  url: '/locations'
  image: office_albany_2.jpg
  text: 'We have offices in Albany, Troy, and Clifton Park dedicated to serving patients throughout and outside the Capital Region with the utmost care and convenience, Monday through Friday from 9:00 am to 4:15 pm. Click below for directions.'
#
# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /getting-started/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#
actionbuttons:
  - callforaction1:
    url: /locations/#contact
    text: Make an appointment
    style: primary
  - callforaction2:
    url: https://www.medentmobile.com/portal/index.php?practice_id=8HPZ85s4
    text: Log in to your Patient Portal
    style: secondary

permalink: /index.html
#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---

<div id="videoModal" class="reveal-modal large" data-reveal="">
  <div class="flex-video widescreen vimeo" style="display: block;">
    <iframe width="1280" height="720" src="https://www.youtube.com/embed/3b5zCFSmVvU" frameborder="0" allowfullscreen></iframe>
  </div>
  <a class="close-reveal-modal">&#215;</a>
</div>
