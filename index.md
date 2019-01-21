---
layout: home
title: Susann's and Erik's wedding
---

# Susann's and Erik's wedding!

Welcome to this small website, about our wedding.

We are planning on using this website for publishing useful information about
our wedding, which takes place on the weekend of 29th of June 2019, in the
village Sayda near Dresden, Germany.

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
