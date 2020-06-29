---
extends: _layouts.post
section: content
title: Shopaholic vs Mall - OctoberCMS eCommerce solutions showdown
date: 2020-06-30
description: In this blog post we compare the two free solutions for e-commerce systems.
cover_image: /assets/img/post-cover-image-2.png
categories: [octobercms,ecommerce,laravel,php]
featured: true
---

Lately I am trying my best to get rid of WooCommerce and Wordpress. I am facing the same issues over and over again and I believe it's time to begin new era in a world of CMS systems. Wordpress is great, but sometimes this just isn't enough.

## Enter the OctoberCMS

October was my latest pick in a long research of what CMS to pick. I really wanted to have a single solution for all my projects needs; no matter it is a simple site, blog or e-commerce solution, I want to use the same thing every time. October seemed like a perfect fit. But was it?

## e-Commerce solutions for OctoberCMS

Checking the e-commerce category on the [plugins site](https://octobercms.com/plugins/e-commerce) you can find the two options: [JKShop](https://octobercms.com/plugin/jiri-jkshop) and [Shopaholic](https://octobercms.com/plugin/lovata-shopaholic). Since Shopaholic is free, I of cousre went with it. And finished the (project)[https://blauberg.si]. But was I satisfied?

## Shopaholic: first impressions

I started the project with a starter theme they provide however I quickly found out that the whole code is just a little complicated to read. It does the job perfectly, however I really wanted to split it up a bit, so I went on with my custom theme. I used the srtarter theme for a reference. All good so far.

Then I had to set up the whole checkout system with credit card option and Stripe as a payment gateway. This part was tricky - I end up creating a custom solution for my needs and went with it - the existing plugins just didn't work. WooCommerce makes this part a breeze.

Then I wanted to email every order to the admin so they could process the orders - and again spent hours to make it work when WooCommerce has it all set up and ready.

So what can I do?

## There is one more player: Mall

While trying to make everything work with Shopaholic, I came around [Mall](https://octobercms.com/plugin/offline-mall). It's kinda hidden but have it's fair share of users. I decided I will give it a test run.

## How do they compare - basics first

Let's check some stats first - obviously, Mall is harder to find since it's number 31 on the free top list of OctoberCMS plugins - while Shopaholic being #10 and also #1 in the e-commerce category. But how about other stats?

Stat                | Shopaholic    | Mall
---                 | ---           | ---
\# of installs      | 10,000+       | 4,000+
Rating              | 4.5           | 5.0
\# of GH stars      | 380           | 106
\# of issues        | 55            | 76
\# of closed issues | 152           | 330

Looks like Shopaholic is a winner in this part. But still, we want to see the Mall in action, to see what it offers out of the box.


