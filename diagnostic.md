# Ember Components Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  Give an example of a visual hierarchy that could be modeled with components. Explain why each piece might be it's own component.

    ```md
    An example of a visual hierarchy would be a list of contacts. The list itself,
    with just names, might have their own components. When you click on a name to
    get additional information, it might generate a new list (new components), perhaps on
    the opposite side of the page, that contain phone number, email, address, etc. The
    separation of these properties of a contact list are contained in separate components
    so that HTML, CSS, and JS can be tied together more efficiently.
    ```

1.  What is the command to generate a new component called '`my-map`'?

    ```sh
    ember generate component my-map
    ```

1.  What files are created and/or edited to produce a component, and what are their responsibilities?

    ```md
    A new component directory and file needs to be created for the sections where you want components.
    So, a list would need a component file, and then the list/item would need a
    component file. In order for the components to communicate appropriately,
    you would need to edit the templates of each component as well.
    ```

1.  Suppose you have a component '`my-contact`', which is loaded from
    '`app/contacts/template.hbs`' when visiting the `/contacts` route. What is
    the syntax (code that is written) to render this component inside that template?

    ```html
    <div>
      {{contacts.my-contact}}
    </div>
    ```

1.  Each contact has multiple phone numbers. Suppose you also have '`my-phone`'
    nested under '`my-contact`'. What is the code you would write in
    '`app/components/my-contact/template.hbs`' to load the nested component and
    pass it data?

    ```html
    <div>
      <h4 class="list-header" {{action 'toggleListDetail'}}>Title: {{list.title}}</h4>
      <ul>
        {{#each contacts.numbers as |number|}}
          {{my-contact/my-phone phone=number}}
        {{/each}}
      </ul>
    </div>
    ```
