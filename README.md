These CSS are designed to work together to create a user interfaces in HTML. This is a very early pass at this work. As you study it, don't focus much on the cosmetics, rather focus on element positioning. As these patterns are refined, the cosmetics can be tweaked. 

This pattern library will grow. It currently doesn't include important patterns such as button or page header patterns. 

Each pattern is currently a separate CSS file--and for initially prototyping working you'll need to include these CSS files. Later, though, these CSS files will be merged into one file. 

These patterns use (and will make more use of CSS custom properties. If you aren't familiar with CSS custom properties, study them. They are very powerful. Read about them [here](https://asna.com/us/tech/kb/doc/css-custom-props) and here[](https://developer.mozilla.org/en-US/docs/Web/CSS/--*).

Briefly, CSS custom properties are a way to define variables in CSS. For example, the CSS below defines a variable named `--max-page-width` which is later used to set the `max-width` of a page. 

    :root {
        --max-page-width: 1280px;
    }

    body {
        max-width: var(--max-page-width);
        ...

CSS custom properties (like all CSS properties) can also have CSS's `calc` function applied to them. For example, if a container half width of the `--max-page-width` is needed, this could easily done as shown below:

    .half-width-container {
        max-width: calc(var(--max-page-width)/2);)
    }

### page-container

The `page-container` pattern provides a fixed-width content panel with left and right margins. This pattern would probably be used only once per page.

###![](https://asna.com/filebin/marketing/IRlKZRtvtv.png)

---

### h-fieldset

The `h-fieldset` pattern is a container for a horizontal field where the field's label is to the left of the field. While textboxes are shown in the example below, fields could also be other elements such as drow-downs, check boxes, or radio buttons. 

![](https://asna.com/filebin/marketing/j0AXgD0oOP.png)

There must be one or more fields provided for this pattern. In example below the customer name is three fields. There is also a place for an error message. If not present, the error message wouldn't show.

`h-fieldset` fields are grouped inside a `div.fields` tag. 

The markup necessary for an `h-fieldset` is shown below. This is the markup that produced the `Customer name` field set below.

```
    <div class="fields">
        <div class="h-fieldset">
            <span>Customer name</span>
            <div class="fields">
                <input type="textbox" />
                <input type="textbox" />
                <input type="textbox" />
            </div>
            <span class="validator">
                Error message
            </span>
        </div>
        ...        
```

---

### v-fieldset.html

The `v-fieldset` pattern is a container for a vertical field where the field's label above the field. Like the `h-fieldset`, fields could also be other elements such as drow-downs, check boxes, or radio buttons. 

![](https://asna.com/filebin/marketing/orAuBOvGGW.png)

There must be one or more fields provided for this pattern. In example below the customer name is three fields. There is also a place for an error message. If not present, the error message wouldn't show.

`h-fieldset` fields are grouped inside a `div.fields` tag. 

The markup necessary for an v-fieldset is shown below. This is the markup that produced the `Customer name` field set below.

```
    <div class="fields">    
        <div class="v-fieldset">
            <span>Customer name</span>
            <div class="fields">
                <input class="" type="textbox" value="Warren Zevon" />
                <input class="w-medium" type="textbox" value="Warren Zevon" />
                <input class="w-small" type="textbox" />
                <input class="w-tiny" type="textbox" />
            </div>
            <span class="validator">
                Error message
            </span>
        </div>
        ...
```
The `v-fieldset` also provides a place for an optional action button displayed above the field. This is the markup for the Contact field. Note how it provides an action button to edit the contact. 

```
    <div class="fields">
        <div class="v-fieldset">
            <div class="horizontal-field-container flex-space-between">
                <span>Contact</span>
                <input type="button" name="EditContact" id="EditContact" class="button-inline-as-link" value="Edit contact" />
            </div>
            <div class="fields">
                <input type="textbox" />
            </div>
            <span class="validator">
                Error message
            </span>
        </div>
        ...
```

---

### column-container
The `column-container` pattern provides two columns within a section of a page. It provides either one or two columns. It is shown below with `h-fieldset` fields.

Note: 

![](https://asna.com/filebin/marketing/n8qv8vUjPw.png)

The `column-container` is shown below with `v-fieldset` fields.

![](https://asna.com/filebin/marketing/dXnKfRk2rX.png)

---

### tabs.html

The `tabs` pattern provides a tabbed user interface. 

![](https://asna.com/filebin/marketing/Q5kP87ExyZ.png)

The markup below produces the tabbed UI shown above. Note that while there is only one `tabbed-section-container` in the markup below, in production use there would be a `tabbed-section-container` for each tab (but only one would be shown at runtime).

```
    <div class="tab-contents-container">
        <div class="tab-buttons-container">
            <input type="button" class="tab-button active-tab" name="Button2" value="Sold/Ship To" id="Button2" />
            <input type="button" class="tab-button" name="Button3" value="Dates/Class/Commission" id="Button3" />
            <input type="button" class="tab-button disabled-tab" name="Button4" value="Order Comments" id="Button4" />
            <input type="button" class="tab-button" name="Button5" value="Line Items" id="Button5" />
            <input type="button" class="tab-button" name="Button5A" value="Special Chg" id="Button5A" />
            <input type="button" class="tab-button" name="Button6" value="Attachments" id="Button6" />
            <input type="button" class="tab-button" name="Button7" value="Tasks/Approvals" id="Button7" />
            <input type="button" class="tab-button" name="Button8" value="Buy Off" id="Button8" />
            <input type="button" class="tab-button" name="Button9" value="F&amp;O.xlsx" id="Button9" />
            <input type="button" class="tab-button" name="Button10" value="Send To COM/ENV" id="Button10" />
        </div>
        <div class="tabbed-section-container">
            Tab section
        </div>
    </div>
```

