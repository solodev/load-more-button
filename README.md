# load-more-button
Showcasing your content on the web is more essential than ever but there's so much content and only so much real estate on a web page before the viewer stops scrolling. Web designers and developers have recognized this behavior in website visitors and implement different techniques to display content in the most intuitive way while still providing the volume of content some visitors may require. 

Your blog may have 1,000 entries but you don't want to show all of them on a single page or it will take an extremely long time to load and cause an information overload that may even increase your bounce rates. In the case of these 1,000 entries developers would likely "lazy load" any entries over a certain integer. In our example, we don't have 1,000 entries so a simple "Load More" button and some JavaScript will suffice. In this article, [Solodev](https://www.solodev.com/) will teach you how to add a load more button to your content.

## Tutorial

For detailed instructions, view Solodev's [Adding a Load More Button to your Content](https://www.solodev.com/blog/web-design/adding-a-load-more-button-to-your-content.stml) article.

## Demo

Try out a working example on [JSFiddle](https://jsfiddle.net/solodev/amuqsu9t/).

## HTML

The load more button contains the following HTML markup.

```
<div class="interior container clearfix">
   <div class="row"> 
      <div class="col-xs-12 col-sm-6 col-md-12 blogBox">
         <div class="item featured">
            <img src="https://www.solodev.com/assets/fancy/travel3.jpg">
            <div class="blogTxt">
               <div class="blogCategory">
                  <a href="/">Business Intelligence</a>
               </div>
               <h2>
                  Eu qui dolore altera, saepe molestie accusamus
               </h2>
               <p class="post_intro hidden-xs">
                  An erant partem albucius quo, ad graece latine atomorum sea, sit dicant laoreet at. Id has chor...
               </p>
            </div>
         </div>
      </div>
      <div class="col-xs-12 col-sm-6 col-md-4 blogBox moreBox" >
         <div class="item">
            <img src="https://www.solodev.com/assets/fancy/travel5.jpg">
            <div class="blogTxt">
               <div class="blogCategory">
                  <a href="/">Virtual Reality</a>
               </div>
               <h2>
                  Ea delicata deterru isset concluda turque
               </h2>
               <p class="post_intro hidden-xs">
                  Mel ut enim atqui, ne eum tation populo delectus. Vim soluta insolens phaedrum et, lucilius par...
               </p>
            </div>
         </div>
      </div>
      <div class="col-xs-12 col-sm-6 col-md-4 blogBox moreBox" >
         <div class="item">
            <img src="https://www.solodev.com/assets/fancy/travel6.jpg">
            <div class="blogTxt">
               <div class="blogCategory">
                  <a href="/">Internet of Things (IoT)</a>
               </div>
               <h2>
                  No vim quis quodsi, etiam quaestio euripidis
               </h2>
               <p class="post_intro hidden-xs">
                  Sed possim nonumes no, iuvaret similique quo no. Ut sea idque option aliquando. Ei mea choro ap...
               </p>
            </div>
         </div>
      </div>
      <div class="col-xs-12 col-sm-6 col-md-4 blogBox moreBox" >
         <div class="item">
            <img src="https://www.solodev.com/assets/fancy/travel9.jpg">
            <div class="blogTxt">
               <div class="blogCategory">
                  <a href="/">Artifical Intelligence</a>
               </div>
               <h2>
                  Qui an alii magna consectetuer
               </h2>
               <p class="post_intro hidden-xs">
                  Ad populo appareat vulputate vix, ex fastidii signiferumque pro. In sea doming reprehendunt. Na...
               </p>
            </div>
         </div>
      </div>
      <div class="col-xs-12 col-sm-6 col-md-4 blogBox moreBox" style="display: none;">
         <div class="item">
            <img src="https://www.solodev.com/assets/fancy/travel7.jpg">
            <div class="blogTxt">
               <div class="blogCategory">
                  <a href="/">Big Data</a>
               </div>
               <h2>
                  Integre voluptatum cu quo iriure docendi senserit
               </h2>
               <p class="post_intro hidden-xs">
                  Delicata inciderint at per, eu partem principes eum, illud nobis appetere ex his. Ei vix melior...
               </p>
            </div>
         </div>
      </div>
      <div class="col-xs-12 col-sm-6 col-md-4 blogBox moreBox" style="display: none;">
         <div class="item">
            <img src="https://www.solodev.com/assets/fancy/travel8.jpg">
            <div class="blogTxt">
               <div class="blogCategory">
                  <a href="/">Growth Hacking</a>
               </div>
               <h2>
                  Pro brute causae aliquip ad
               </h2>
               <p class="post_intro hidden-xs">
                  No ipsum invidunt eos, ei ius dicit platonem perpetua. Mea te feugait ocurreret aliquando, ei i...
               </p>
            </div>
         </div>
      </div>
      <div class="col-xs-12 col-sm-6 col-md-4 blogBox moreBox" style="display: none;">
         <div class="item">
            <img src="https://www.solodev.com/assets/fancy/travel2.jpg">
            <div class="blogTxt">
               <div class="blogCategory">
                  <a href="/">Content Marketing</a>
               </div>
               <h2>
                  Lorem ipsum dolor sit amet, consect adipiscing elit
               </h2>
               <p class="post_intro hidden-xs">
                  Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam, nisi ...
               </p>
            </div>
         </div>
      </div>
      <div id="loadMore" style="">
         <a href="#">Load More</a>
      </div>
   </div>
</div>
```

## CSS

All necessary CSS is included in the file load-more-button.css

## JavaScript

The load more button utilizes the following JavaScript.

```
$( document ).ready(function () {
                $(".moreBox").slice(0, 3).show();
                if ($(".blogBox:hidden").length != 0) {
                        $("#loadMore").show();
                }               
                $("#loadMore").on('click', function (e) {
                        e.preventDefault();
                        $(".moreBox:hidden").slice(0, 6).slideDown();
                        if ($(".moreBox:hidden").length == 0) {
                                $("#loadMore").fadeOut('slow');
                        }
                });
        });
```

## External Includes

This tutorial contains the following third party resources.

```
<link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" rel="stylesheet">
<link href="load-more-button.css" rel="stylesheet">
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
```
