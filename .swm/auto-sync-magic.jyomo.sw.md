---
title: "\U0001F984 Auto-sync magic "
---
## What happens when your code changes?

When your code changes, Swimm determines if it’s a minor or major change, and your doc is updated.

| Change type  | Examples                                                                                      | Detection | Manual Action                    | Automated |
| ------------ | --------------------------------------------------------------------------------------------- | --------- | -------------------------------- | --------- |
| Minor change | · A **line change**<br><br>· Renaming a **variable**<br><br>· A change of **key-value** pairs | ✅        | Accept Swimm’s<br><br>suggestion | ✅        |
| Major change | · The **function** was deleted<br><br>· The line **completely changed**                       | ✅        | Accept Swimm’s<br><br>suggestion | ❌        |

&nbsp;

### Minor Change

In the example below Swimm detected a minor change in the code.

The developer changed 2 things:

- An "<li>" element to a "<div>".

- Added a css class "view-template".

Swimm detects code changes and shows the diff.

In order to fix the snippets below, go to edit mode.

**Click "Accept" to "fix" it**.

<SwmSnippet path="/examples/vanilla-es6/src/template.js" line="21">

---

This code creates a dynamic HTML list <SwmToken path="/examples/vanilla-es6/src/template.js" pos="21:10:10" line-data="&lt;li data-id=&quot;${item.id}&quot;${item.completed ? &#39; class=&quot;completed&quot;&#39; : &#39;&#39;}&gt;">`item`</SwmToken> element using JavaScript template literals and data from an item object.\
&nbsp;we're using the <SwmToken path="/examples/vanilla-es6/src/template.js" pos="24:5:5" line-data="		&lt;label&gt;${escapeForHTML(item.title)}&lt;/label&gt;">`escapeForHTML`</SwmToken> helper function to replaces '&' and '<' with their HTML entity equivalents to prevent XSS.

```javascript
<li data-id="${item.id}"${item.completed ? ' class="completed"' : ''}>
	<div class="view">
		<input class="toggle" type="checkbox" ${item.completed ? 'checked' : ''}>
		<label>${escapeForHTML(item.title)}</label>
		<button class="destroy"></button>
	</div>
</li>`, '');
```

---

</SwmSnippet>

&nbsp;

### Major Change

In this example, the function has been completely refactored and and Swimm considers this a major change.

At this point, the person familiar with change should get a decision. Either to replace this snippet to the correct one, or remove it.

**Fix this snippet 👇 - use the "Reselect" button below...**

<SwmSnippet path="/examples/vanilla-es6/src/store.js" line="53">

---

This function <SwmToken path="/examples/vanilla-es6/src/store.js" pos="53:1:1" line-data="	find(query, callback) {">`find`</SwmToken> and <SwmToken path="/examples/vanilla-es6/src/store.js" pos="57:5:5" line-data="		callback(todos.filter(todo =&gt; {">`filter`</SwmToken> objects in the <SwmToken path="/examples/vanilla-es6/src/store.js" pos="54:3:3" line-data="		const todos = this.getLocalStorage();">`todos`</SwmToken> array based on matching key-value pairs in a query object and passes the result to a callback function.

```javascript
	find(query, callback) {
		const todos = this.getLocalStorage();
		let k;

		callback(todos.filter(todo => {
			for (k in query) {
				if (query[k] !== todo[k]) {
					return false;
				}
			}
			return true;
		}));
	}
```

---

</SwmSnippet>

&nbsp;

## Voila!

Your code-coupled elements are now updated in your doc.

**The next step** would be to commit your changes to your repository, open a pull request and merge your branches for your team to have the latest documentation.

&nbsp;

&nbsp;

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZ2l0aHViLXRlc3QxJTNBJTNBU2hhdWxBbXJhblM=" repo-name="github-test1"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
