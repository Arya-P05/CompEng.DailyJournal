---
layout: page
title: Final Thoughts - Video
tagline: Arya Patell
---

<div class="blogwidevideo">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/grB4pnZB3W4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

.blogwidevideo {    
    overflow:hidden;
    padding-bottom:56.25%;
    position:relative;
    height:0;    
}

.blogwidevideo iframe {   
    left:10%; //centers for the 80% width - not needed if width is 100%
    top:0;
    height:80%; //change to 100% if going full width
    width:80%;
    position:absolute;
}
