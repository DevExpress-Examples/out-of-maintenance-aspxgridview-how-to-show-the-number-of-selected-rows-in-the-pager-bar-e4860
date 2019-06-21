<!-- default file list -->
*Files to look at*:

* [Default.aspx](./CS/WebSite/Default.aspx) (VB: [Default.aspx](./VB/WebSite/Default.aspx))
* [Default.aspx.cs](./CS/WebSite/Default.aspx.cs) (VB: [Default.aspx.vb](./VB/WebSite/Default.aspx.vb))
<!-- default file list end -->
# ASPxGridView - How to show the number of selected rows in the Pager bar
<!-- run online -->
**[[Run Online]](https://codecentral.devexpress.com/e4860/)**
<!-- run online end -->


<p>This example demonstrates how to show the number of selected rows in the Pager bar.  It is necessary to create a custom <a href="http://documentation.devexpress.com/#AspNet/DevExpressWebASPxGridViewGridViewTemplates_PagerBartopic"><u>PagerBar</u></a> template for this purpose. This template will contain ASPxLabel that allows showing the number of selected rows and a standard pager created via the  <a href="http://documentation.devexpress.com/#AspNet/DevExpressWebASPxGridViewASPxGridViewTemplateReplacementMembersTopicAll"><u>ASPxGridViewTemplateReplacement</u></a> control:<u><br />
</u><u><br />
</u>

```aspx
<PagerBar>
	<table>
		<tr>
			<td>
				<dx:ASPxGridViewTemplateReplacement runat="server" ReplacementType="Pager" />
			</td>
			<td>
				<dx:ASPxLabel ID="labelInfo" runat="server" Text="" ClientInstanceName="labelInfo">
				</dx:ASPxLabel>
			</td>
		</tr>
	</table>
</PagerBar>
```

 </p><p>We can get the grid's selected row count via the client-side <a href="http://documentation.devexpress.com/#AspNet/DevExpressWebASPxGridViewScriptsASPxClientGridView_GetSelectedRowCounttopic"><u>ASPxClientGridView.GetSelectedRowCount</u></a> method and then set it to ASPxLabel using the label's <a href="http://documentation.devexpress.com/#AspNet/DevExpressWebASPxEditorsScriptsASPxClientLabel_SetTexttopic"><u>SetText</u></a> method:<br />


```js

        function ShowRowsCount() {
            labelInfo.SetText('Selected rows count: ' + gridView.GetSelectedRowCount());
        } 
```

 </p>

<br/>


