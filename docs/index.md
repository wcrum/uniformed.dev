---
hide:
  - toc
  - navigation
---

<h1 style="font-weight: 300" align="center" class="typerheader">
 We are a community of
  <a style="font-weight: 400" href="#" class="typewrite" data-period="2000" data-type='[ "Developers.", "Marines.", "Sailors.", "Engineers.", "Airmen.", "Innovators.", "Guardians.", "Veterans."]'>
    <span class="wrap"></span>
  </a>
</h1>
<h4 align="center" style="font-weight: 100 !important;">
  <em>- A place for service members to collaborate and innovate within the Department of Defense.</em>
</h4>

<div class="cards grid special" markdown>

-   [:material-factory:{ .lg .middle } __Software Factories__](/swf)

-   [:fontawesome-solid-people-group:{ .lg .middle } __Join a Community__](/communities)

-   [:octicons-organization-24:{ .lg .middle } __Find an Organization__](/organizations)

-   [:material-tools:{ .lg .middle } __Learn about Projects__](/projects)

</div>

</br>

<style>
@media only screen and (max-width: 600px) {
    .special {
        grid-gap: .4rem;
        display: grid;
        grid-template-columns: repeat(auto-fit,minmax(10rem,1fr)) !important;
        margin: 1em 0;
    }
}
@media only screen and (min-width: 600px) {
    .special {
        grid-gap: .4rem;
        display: grid;
        grid-template-columns: repeat(auto-fit,minmax(4rem,1fr)) !important;
        margin: 1em 0;
    }
}

.special li {
    text-align: center;
}

.special a {
    display: block;
}

@media only screen and (max-width: 600px) {
    .md-typeset .grid {
        grid-gap: .4rem;
        display: grid;
        grid-template-columns: repeat(auto-fit,minmax(16rem,1fr));
        margin: 1em 0;
    }
}
@media only screen and (min-width: 600px) {
    .md-typeset .grid {
        grid-gap: .4rem;
        display: grid;
        grid-template-columns: repeat(auto-fit,minmax(20rem,1fr));
        margin: 1em 0;
    }
}
</style>

<script>
var TxtType = function(el, toRotate, period) {
        this.toRotate = toRotate;
        this.el = el;
        this.loopNum = 0;
        this.period = parseInt(period, 10) || 2000;
        this.txt = '';
        this.tick();
        this.isDeleting = false;
    };

    TxtType.prototype.tick = function() {
        var i = this.loopNum % this.toRotate.length;
        var fullTxt = this.toRotate[i];

        if (this.isDeleting) {
        this.txt = fullTxt.substring(0, this.txt.length - 1);
        } else {
        this.txt = fullTxt.substring(0, this.txt.length + 1);
        }

        this.el.innerHTML = '<span class="wrap">'+this.txt+'</span>';

        var that = this;
        var delta = 200 - Math.random() * 100;

        if (this.isDeleting) { delta /= 2; }

        if (!this.isDeleting && this.txt === fullTxt) {
        delta = this.period;
        this.isDeleting = true;
        } else if (this.isDeleting && this.txt === '') {
        this.isDeleting = false;
        this.loopNum++;
        delta = 500;
        }

        setTimeout(function() {
        that.tick();
        }, delta);
    };

    window.onload = function() {
        var elements = document.getElementsByClassName('typewrite');
        for (var i=0; i<elements.length; i++) {
            var toRotate = elements[i].getAttribute('data-type');
            var period = elements[i].getAttribute('data-period');
            if (toRotate) {
              new TxtType(elements[i], JSON.parse(toRotate), period);
            }
        }
        // INJECT CSS
        var css = document.createElement("style");
        css.type = "text/css";
        css.innerHTML = ".typewrite > .wrap { border-right: 0.08em solid #aaa}";
        document.body.appendChild(css);
    };
</script>