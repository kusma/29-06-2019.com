---
layout: home
title: Susann's and Erik's wedding
---

<div id="countdown" class="h2 mx-auto w-100 text-center mb-5"></div>

# Susann's and Erik's Wedding!

Welcome to this small website, about our wedding.

We are planning on using this website for publishing useful information about
our wedding, which takes place on the weekend of 29th of June 2019, in the
village Sayda near Dresden, Germany.

## Where?

The venue for our wedding is [Altsächsischer Gasthof Kleines Vorwerk](https://www.kleines-vorwerk.de/),
which you can see on the maps below.

We have booked the entire place, which provides accommodation for all of the
guests. Additionally, we have reserved 4 extra rooms at the nearest bed &
breakfast, in case someone wants to live a bit more privately.

<div id="venue-map" class="row">
  <iframe class="embed-responsive-item" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d322574.75213734654!2d13.167321244366743!3d50.829823675707395!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x4709faf0ac42353b%3A0xa9716480daa2b72c!2sAlts%C3%A4chsischer+Gasthof+Kleines+Vorwerk!5e0!3m2!1sen!2sno!4v1548194453426" frameborder="0" allowfullscreen></iframe>
</div>

<div id="venue-map-2" class="row pt-4 d-block">
<img class="img-fluid w-100" src="{% link /assets/venue-map.svg %}" alt="map of venue">
</div>

## Weather forecast

Here's the weather for the next 7 days in Sayda:

<a class="weatherwidget-io" href="https://forecast7.com/en/50d7113d42/sayda/" data-font="Noto Sans" data-icons="Climacons Animated" data-mode="Forecast" data-theme="original" data-basecolor="rgba(0, 0, 0, 0)" data-accent="rgba(88, 14, 26, 0.02)" data-textcolor="#00716f" data-highcolor="#b6003a" data-lowcolor="#00549f" data-suncolor="#b68e00" data-mooncolor="#7487bc" data-cloudcolor="#9e9e9e" data-cloudfill="#d0d0d0" data-raincolor="#00549f" >Sayda, Germany</a>
<script>
!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0];if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src='https://weatherwidget.io/js/widget.min.js';fjs.parentNode.insertBefore(js,fjs);}}(document,'script','weatherwidget-io-js');
</script>

## Timetable

Here's a tentative timetable of the activities of our big event. Times may
change a bit, but we'll try to keep things as predictable as we can.

<div class="row">
<div class="col-md-4" markdown="1">

### Friday

| When    | What                                                        |
|---------|-------------------------------------------------------------|
| All day | <i class="fas fa-plane-arrival"></i> Guests arrive in Sayda |
| 20:00   | <i class="fas fa-glass-martini-alt"></i> Meet & greet       |

</div>
<div class="col-md-4" markdown="1">

### Saturday

| When  | What                                                |
|-------|-----------------------------------------------------|
| 09:00 | <i class="fas fa-mug-hot"></i> Breakfast (optional) |
| 15:00 | <i class="fas fa-heart"></i> Wedding ceremony       |
| 18:00 | <i class="fas fa-utensils"></i> Dinner              |
| 22:00 | <i class="fas fa-glass-cheers"></i> Party           |

</div>
<div class="col-md-4" markdown="1">

### Sunday

| When    | What                                                       |
|---------|------------------------------------------------------------|
| All day | <i class="fas fa-plane-departure"></i> Guests depart Sayda |
| 11:00   | <i class="fas fa-mug-hot"></i> Brunch (optional)           |

</div>
</div>

## Dress code

Generally speaking, the dress code is "dressy casual", which is defined as
"somewhere between formal and casual". This means suits or sports coats for
the guys, but a tie is optional. For the girls, it means a cocktail dress or
a dressy skirt and top.

This is a summer-wedding, and it's usually pretty warm in Sayda around this
time of year. So keep that in mind, and dress accordingly. Also, ladies:
because we will spend the evening on a lawn, we don't recommend wearing
stilettos... You might regret it! Besides, dancing-shoes are more fun!

## Flights

We have searched for some flight options for you, and here's the best ones we
found!

There are no direct flights to Dresden. Flying there with a layover is
drastically more expensive. Therefore, we recommend flying to Berlin instead,
and taking some other transportation to Sayda.

We have looked into rental car costs, and we would recommend people to get
together and share bigger cars. There are for instance 9 seaters available
for around 200€ for the entire weekend. We can help coordinate this, just
contact us!

### Direct Flights (Oslo - Berlin - Oslo)

{% for airline in site.data.direct_flights %}
<h4>{{ airline.name }}</h4>

<div class="row">

{% for direction in airline.directions %}

<div class="col-md-6">
<h5>{{ direction.date | date: '%B %d, %Y' }}, {{ direction.from }} to {{ direction.to }} </h5>

<table class="table">
  <thead>
    <tr>
      <th scope="col">time</th>
      <th scope="col">code</th>
    </tr>
  </thead>
  <tbody>

  {% for option in direction.options %}
  <tr>
    <td>{{ option.departure-time }} - {{ option.arrival-time }}</td>
    <td>{{ option.codes | join: ' / ' }}</td>
  </tr>
  {% endfor %}

  </tbody>
</table>

</div>

{% endfor %}

</div>

{% endfor %}

### Flights with layover (Oslo - Dresden - Oslo)

{% for airline in site.data.layover_flights %}
<h4>{{ airline.name }}</h4>

<div class="row">

{% for direction in airline.directions %}

<div class="col-md-6">
<h5>{{ direction.date | date: '%B %d, %Y' }}, {{ direction.from }} to {{ direction.to }} </h5>

<table>
  <thead>
    <tr>
      <th scope="col">time</th>
      <th scope="col">layover</th>
      <th scope="col">code</th>
    </tr>
  </thead>
  <tbody>

  {% for option in direction.options %}
  <tr>
    <td>{{ option.departure-time }} - {{ option.arrival-time }}</td>
    <td>{{ option.layover }} ({{ option.layover-time }})</td>
    <td>{{ option.codes | join: ' / ' }}</td>
  </tr>
  {% endfor %}

  </tbody>
</table>

</div>

{% endfor %}

</div>

{% endfor %}

<script>
  var target = new Date('June 29, 2019 15:00 (UTC)');
  var countdown = document.getElementById('countdown');

  function updateCountdown() {
    var now = new Date();
    var diff = target - now;
    if (diff < 0) {
      countdown.innerHTML = '';
      return false;
    }

    function pluralize(num, word) {
      return num + " " + (num == 1 ? word : word + 's');
    }

    var days = Math.floor(diff / (1000 * 60 * 60 * 24));
    var hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    var minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
    var seconds = Math.floor((diff % (1000 * 60)) / 1000);
    var strings = [
      pluralize(days, 'day'),
      pluralize(hours, 'hour'),
      pluralize(minutes, 'minute'),
      pluralize(seconds, 'second'),
    ];
    countdown.innerHTML = strings.slice(0, -1).join(', ') + ' and ' + strings.slice(-1);
    return true;
  }

  if (updateCountdown()) {
    var i = setInterval(function() {
      if (!updateCountdown())
        clearInterval(i);
    }, 1000);
  }
</script>
