# Ad Group Best Practices for PMP Deals in TTD

Follow these steps to create a new Ad Group that targets a Chalice PMP deal exclusively. This ensures your budget is directed to the deal inventory and not competing with open exchange.

---

## Step 1. Enable "Prioritize Deal" on the Endeavor

After you [accept the PMP deal in your Deal Desk](accepting-a-pmp-deal.md), click on your deal and go to **Endeavor Performance**. Scroll down and toggle **Prioritize Deal** to on.

!!! tip
    Enabling "Prioritize Deal" ensures TTD sends eligible bid requests to this deal before considering open exchange inventory.

![Prioritize deal toggle in Endeavor Performance tab](assets/ttd-prioritize-deal.jpg)

---

## Step 2. Create a new Ad Group

Select **Start with Ad Group Name** when prompted.

---

## Step 3. Enter the Ad Group name and add it

Enter a descriptive Ad Group name that references the deal (e.g., `Chalice PMP - [Deal ID] - [Campaign]`). Click **Add Ad Groups**.

---

## Step 4. Edit Inventory settings

Once your Ad Group appears in the list, click **Edit Inventory**.

---

## Step 5. Set inventory to "Deals only" and add the deal

1. Click **Deals only**
2. Click **Add Deals**
3. Set the following filters:
    - **View by:** Deals
    - **Deal Type:** Endeavor
    - **Deal Status:** All
    - **Selling Party:** Chalice
    - Or search by Deal ID using the search icon
4. Select your deal by clicking the **+** icon, then click **Add selected deals**

---

## Step 6. Confirm and save

Back on the **Manage Inventory** screen, confirm your deal is selected. Click **Save**.

---

## Step 7. Generate Ad Groups

Once all Ad Group settings are configured, click **Generate Ad Groups**.

<details class="bid-matrix">
<summary style="cursor:pointer; font-weight:600;">Suggested CPM bids by country and channel</summary>
<p>Your Chalice support team will provide tailored bid recommendations for your ad group. Standard bid guidance by country is listed below. Use the selector to view it in another currency.</p>
<p style="margin:0.75rem 0;">
<label for="bid-currency" style="margin-right:6px;">Currency</label>
<select id="bid-currency">
<option value="USD">USD ($)</option>
<option value="EUR">EUR (&euro;)</option>
<option value="GBP">GBP (&pound;)</option>
<option value="DKK">DKK (kr)</option>
<option value="NOK">NOK (kr)</option>
</select>
<span id="bid-rate-note" style="margin-left:8px; font-size:0.8em; opacity:0.7;"></span>
</p>
<table id="bid-table">
<thead><tr><th>Country</th><th>Display CPM</th><th>Video CPM</th></tr></thead>
<tbody>
<tr><td>Denmark</td><td class="bid" data-usd="1">$1.00</td><td class="bid" data-usd="4">$4.00</td></tr>
<tr><td>France</td><td class="bid" data-usd="4">$4.00</td><td class="bid" data-usd="5">$5.00</td></tr>
<tr><td>Norway</td><td class="bid" data-usd="5">$5.00</td><td class="bid" data-usd="6">$6.00</td></tr>
<tr><td>Spain</td><td class="bid" data-usd="3">$3.00</td><td class="bid" data-usd="4">$4.00</td></tr>
<tr><td>UK</td><td class="bid" data-usd="3">$3.00</td><td class="bid" data-usd="7">$7.00</td></tr>
<tr><td>US</td><td class="bid" data-usd="4">$4.00</td><td class="bid" data-usd="7">$7.00</td></tr>
</tbody>
</table>
</details>

<script>
(function(){
  var rates={USD:1,EUR:0.880805,GBP:0.759731,DKK:6.575862,NOK:9.849377};
  var asOf="Jun 25, 2026", live=false;
  function fmt(usd,cur){return new Intl.NumberFormat("en",{style:"currency",currency:cur,maximumFractionDigits:2}).format(usd*rates[cur]);}
  function render(){
    var sel=document.getElementById("bid-currency"); if(!sel)return;
    var cur=sel.value;
    document.querySelectorAll("#bid-table td.bid").forEach(function(td){
      td.textContent=fmt(parseFloat(td.getAttribute("data-usd")),cur);
    });
    var note=document.getElementById("bid-rate-note");
    if(note)note.textContent=cur==="USD"?"Base rates in USD":(live?"Converted using live rates":"Converted from USD, rates as of "+asOf);
  }
  function init(){
    var sel=document.getElementById("bid-currency"); if(!sel)return;
    sel.addEventListener("change",render); render();
    fetch("https://open.er-api.com/v6/latest/USD").then(function(r){return r.json();}).then(function(d){
      if(d&&d.rates){["EUR","GBP","DKK","NOK"].forEach(function(c){if(d.rates[c])rates[c]=d.rates[c];}); live=true; render();}
    }).catch(function(){});
  }
  if(document.readyState!=="loading")init(); else document.addEventListener("DOMContentLoaded",init);
})();
</script>

---

## Step 8. Verify in your Campaign

Navigate to your Campaign. In the Ad Group, under **Inventory Selection**, you should see the deal listed and selected.

!!! warning
    If the deal does not appear under Inventory Selection, go back and confirm the deal was accepted in the Deal Desk and that "Deals only" was selected in Step 5.

---

## Related articles

- [Accepting a PMP Deal in TTD](accepting-a-pmp-deal.md)
