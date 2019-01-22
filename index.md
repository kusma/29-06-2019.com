---
layout: home
title: Susann's and Erik's wedding
---

# Susann's and Erik's Wedding!

Welcome to this small website, about our wedding.

We are planning on using this website for publishing useful information about
our wedding, which takes place on the weekend of 29th of June 2019, in the
village Sayda near Dresden, Germany.

## Where?

The venue for our wedding is [Altsächsischer Gasthof Kleines Vorwerk](https://www.kleines-vorwerk.de/),
which you can see on the map below.

We have booked the entire place, which provides accommodation for most of the
guests. Don't worry, we already reserved 4 extra rooms at the nearest bed &
breakfast, which is enough for everyone!

<div id="venue-map" class="row">
  <iframe class="embed-responsive-item" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d322574.75213734654!2d13.167321244366743!3d50.829823675707395!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x4709faf0ac42353b%3A0xa9716480daa2b72c!2sAlts%C3%A4chsischer+Gasthof+Kleines+Vorwerk!5e0!3m2!1sen!2sno!4v1548194453426" frameborder="0" allowfullscreen></iframe>
</div>

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

<table class="table">
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
