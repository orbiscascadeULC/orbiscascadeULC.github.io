---
title: Harvester Email
date: 2019-09-25 18:35:00 Z
layout: page
---

{% for p in site.data.harvester %}
***

{{p.name}},  {{p.org}}

Email: [{{p.email}}](mailto:{{p.email}}?subject=Two short Questions on Alliance harvester datasets)


Dear {{p.name | split: " " | first}},


Members of the ULC team and the Orbis Cascade Alliance Central staff have recently begun investigating the steps necessary to re-start our work with DPLA. 

The Alliance paused the DPLA project in 2018 due to several extenuating circumstances. We had, by that time, however, been accepted as a DPLA hub, and we were beginning to do our initial uploads to DPLA. For this process, we used a "harvester" that we built in-house with grant funds. 

We are currently examining the data that was harvested during that initial push via the harvester, and you are receiving this email because your institution contributed some of that data.

Thank you very much for contributing to the project! If you wouldn't mind, would you please answer a couple questions about the data you submitted:

- Are you the contact person for this material? (If not, please let us know the appropriate contact.)
- Has any of your metadata (or the underlying system providing it) changed in such a way that you would need to "reload" more accurate data?

Here's some data regarding your contribution. 

**{{p.org}} submitted {{p.number}} items to be harvested,** including the following sets: 

{%- assign sets = site.data.all | where_exp: "item", 'item.publisher == p.org' -%}
{% for s in sets  %}
- *{{s.title}}*, {{s.number}} objects (last contributed in {{s.date}})
{%endfor%}

We will be working these next couple months to get a better grasp on the steps necessary to get our DPLA ingestion program back up and running. After our investigation, we will be putting a recommendation to the board regarding our ongoing commitments to this process.

If you have any comments or questions about this process or the project in general, please feel free to share them with us. We welcome any insight members of the community might have.

And thank you for your patience with this project. We know you spent time and effort preparing this data for harvest and investing in the program previously. Now that the Alliance is on solid ground (and so is DPLA, in regards to their commitment to cultural heritage items), we very much hope we can resume this important work with your help.

Thank you,

Sarah Seymore, ULC DCBP Standing Group Chair

***
{% endfor %}