---
hide:
  - toc
  - navigation
---

<h1 style="font-weight: 300" align="center" class="typerheader">
 We are a community of
  <a style="font-weight: 400" href="#" class="typewrite" data-period="2000" data-type='[ "Developers.", "Marines.", "Sailors.", "Engineers.", "Airmen.", "Guardians.", "Veterans."]'>
    <span class="wrap"></span>
  </a>
</h1>
<h4 align="center" style="font-weight: 100 !important;">
  <em>- A place for service members to collaborate and innovate within the Department of Defense.</em>
</h4>

<div class="grid cards" markdown>

-   __Airmen Coders__

    ---

    ![Airmen Coders Logo](assets/organizations/airmencoders.png){: align="left" style="width:150px;"}
    We are a group of U.S. Air Force Airmen who use code to improve the lives of our fellow Airmen. Airmen Coders is proudly `#PoweredByTron`

    [:octicons-arrow-right-24: Airmen Coders](https://airmencoders.us/)

-   __Supra Coders__

    ---
    ![Supra Coders Logo](assets/organizations/supracoders.png){: align="left" style="width:150px;"}
    U.S. Space Force coders creating innovative, cutting-edge software to enhance warfighter capabilities in an ever-evolving digital domain.

    [:octicons-arrow-right-24: Supra Coders](https://supracoders.us/)

-   __Marine Coders__

    ---
    ![Marine Coders Logo](assets/organizations/marinecoders_small_text_invert.png){: align="left" style="width:150px;"}
    Marine Coders is a non-official organization comprised of Active Duty/Reserve Marines, Marine Veterans, and U.S. Citizens who want to help Marines through code.

    [:octicons-arrow-right-24: Marine Coders](https://marines.dev)

-   __Army Coders__

    ---
    ![Army Coders Logos](assets/organizations/armycoders_logo1.png){: align="left" style="width:150px;"}
    Continuously recylcing the effort and expanding as we go. Building a grassroots effort to connect Soldier Coders to coding and training resources.

    [:octicons-arrow-right-24: Army Coders](https://coders.army/)

</div>

## Software Factories

## Other Organizations

<div class="grid cards" markdown>

-   __Operation Code__

    ---

    ![Operation Code Logos](assets/organizations/large-blue-logo.webp){: align="left" width="150px"}
    We're the largest community of military veterans, service members, and spouses committed to becoming software developers with the help of mentors, scholarships, and our tech partners.

    [:octicons-arrow-right-24: Operation Code](https://operationcode.org/)

-   __The Joint Software Alliance__

    ---
    ![JSOFT Logos](assets/organizations/JSOFT_Logo_Color.webp){: align="left" width="150px"}
    U.S. Space Force coders creating innovative, cutting-edge software to enhance warfighter capabilities in an ever-evolving digital domain.

    [:octicons-arrow-right-24: Joint Software Alliance](https://supracoders.us/)


</div>
<style>
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
        css.innerHTML = ".typewrite > .wrap { border-right: 0.08em solid #fff}";
        document.body.appendChild(css);
    };
</script>