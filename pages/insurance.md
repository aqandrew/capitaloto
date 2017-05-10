---
layout: page
title: Insurance
permalink: /insurance/
---
Most plans require co-payments; some plans require referrals and/or have high deductibles. If you are unsure about the requirements of your plan, please contact your insurance carrier prior to your appointment.

As a reminder, please remember to bring your insurance card, any referrals, and a list of current medications you are taking to your appointment. We collect co-payments at the time of your visit.

**Note**: If your insurance plan has a *high deductible which you have not met*, please be prepared to make the following payments at the time of your visit:

<div class="center">
  <ul>
    <li>
      $175.00 for new patients
    </li>
    <li>
      $75.00 for existing patients
    </li>
  </ul>
</div>

We look forward to your visit!

### Most commonly accepted insurance carriers
Each company listed below may have multiple plans that we accept. This list is subject to change; please call our office at [(518)482-9111](tel:(518)482-9111) to verify coverage if you are unsure we accept your plan, or if you do not see your insurance company listed below.

<div class="center">
<ul>
  {% for insurance in site.data.insurance %}
  <li>
    {{ insurance.name }}
  </li>
  {% endfor %}
</ul>
</div>

### Notice regarding diagnostic procedures

Procedures such as laryngoscopy or endoscopy performed during your examination may be considered a **surgical** procedure under your health insurance plan. As such, they can be subject to a **deductible or co-pay that is significantly higher than the normal co-pay**. Please check with your insurance plan if you have any questions.

If you have coverage through the following insurances, they typically charge it to your deductible. The deductible amounts vary, and you should contact your insurance with any questions regarding the amount that will be charged.

{% for insurance in site.data.insurance %}
  {% if insurance.diagnostic_deductible %}- {{ insurance.name }}{% endif %}
{% endfor %}

There may be other insurances that apply a deductible, as plans can change from month to month.
