# Sales Commission Calculator
<br>
<section class="body"> Input the number of each item sold. <div class="row"> <form name="myform"> <div class="one-half column"> <table> <thead> <tr> <th style="text-align:left">Item</th> <th style="text-align:center">Price</th> <th style="text-align:center">Number Sold</th> <th style="text-align:right">Totals</th> </tr> </thead> <tbody> <tr> <td style="text-align:left">1</td> <td style="text-align:center">$239.99</td> <td style="text-align:center"><input type="number" name="item1" min="0" max="1000" step="1" required=""></td> <td style="text-align:right"><div id="item1">0.00</div></td> </tr> <tr> <td style="text-align:left">2</td> <td style="text-align:center">$129.75</td> <td style="text-align:center"><input type="number" name="item2" min="0" max="1000" step="1" required=""></td> <td style="text-align:right"><div id="item2">0.00</div></td> </tr> <tr> <td style="text-align:left">3</td> <td style="text-align:center">$99.95</td> <td style="text-align:center"><input type="number" name="item3" min="0" max="1000" step="1" required=""></td> <td style="text-align:right"><div id="item3">0.00</div></td> </tr> <tr> <td style="text-align:left">4</td> <td style="text-align:center">$350.89</td> <td style="text-align:center"><input type="number" name="item4" min="0" max="1000" step="1" required=""></td> <td style="text-align:right"><div id="item4">0.00</div></td> </tr> <tr> <td style="text-align:left"><strong>Total</strong></td> <td style="text-align:center"><strong>Amount</strong></td> <td style="text-align:center"><strong>Sold</strong></td> <td style="text-align:right"><div id="totalSold">0.00</div></td> </tr> <tr> <td style="text-align:left"><strong>Total</strong></td> <td style="text-align:center"><strong>Weekly</strong></td> <td style="text-align:center"><strong>Earnings</strong></td> <td style="text-align:right"><div id="totalEarnings">0.00</div></td> </tr> </tbody> </table> </div> <div class="one-half column"> <br><br> <div id="salesperson"><div class="tooltip"><label for="salesperson">Salesperson:</label><br> <input type="text" id="salesperson" name="salesperson" required=""><span class="tooltiptext"> Pay Attention to spelling </span></div></div> <span class="button-row"> <input type="button" class="button-primary" onclick="calc()" value="Submit"> <input type="reset" class="button" value="Reset" id="reset"> </span> <br> <div id="messages"></div> <br> </div> </form> </div> </section>
<script>
  const displayResults=(e="",t=0,n=0,s=0,o=0,i=0,l=0)=>{document.getElementById("messages").textContent=e,document.getElementById("item1").textContent=t.toFixed(2),document.getElementById("item2").textContent=n.toFixed(2),document.getElementById("item3").textContent=s.toFixed(2),document.getElementById("item4").textContent=o.toFixed(2),document.getElementById("totalSold").textContent=i.toFixed(2),document.getElementById("totalEarnings").textContent=l.toFixed(2)};function calc(){let e={i1:parseFloat(document.forms.myform.elements.item1.value),i2:parseFloat(document.forms.myform.elements.item2.value),i3:parseFloat(document.forms.myform.elements.item3.value),i4:parseFloat(document.forms.myform.elements.item4.value),salesperson:document.forms.myform.elements.salesperson.value,i1t:()=>Math.round(23999*e.i1)/100,i2t:()=>Math.round(12975*e.i2)/100,i3t:()=>Math.round(9995*e.i3)/100,i4t:()=>Math.round(35089*e.i4)/100,ts:()=>e.i1t()+e.i2t()+e.i3t()+e.i4t(),te:()=>.09*e.ts()+200};Number.isNaN(e.i1)||Number.isNaN(e.i2)||Number.isNaN(e.i3)||Number.isNaN(e.i4)||0>e.i1||0>e.i2||0>e.i3||0>e.i4||""==e.salesperson?displayResults("Invalid input! You can't sell less than none of any item, and your salesperson needs a name."):displayResults("",e.i1t(),e.i2t(),e.i3t(),e.i4t(),e.ts(),e.te())}document.getElementById("salesperson").innerHTML='<div class="tooltip"><label for="salesperson">Salesperson:</label><br> <input type="text" id="salesperson" name="salesperson" required><span class="tooltiptext">Please be cognizant of spelling!</div>',document.getElementById("reset").addEventListener("click",(()=>{displayResults()})),displayResults()
  </script>
