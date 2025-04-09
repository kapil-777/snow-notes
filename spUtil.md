
## **What is `spUtil`?**

`spUtil` is a **client-side utility object** in ServiceNow's **Service Portal** that provides **helper methods** to:
- Show messages (info, error, trivial)
- Handle modals
- Scroll to sections
- Update breadcrumbs and URLs
- Perform HTTP requests (GET/POST)
- Interact with live data using `recordWatch`

It helps simplify **UI-related operations** inside **widget client controllers**.

---

## **Common `spUtil` Methods**

---

### **1. `spUtil.addInfoMessage(message)`**

**Definition:** Displays a blue **info message** at the top of the page (like system notifications).

**Example:**
```javascript
spUtil.addInfoMessage("Data saved successfully.");
```

---

### **2. `spUtil.addErrorMessage(message)`**

**Definition:** Displays a red **error message**, usually when something fails.

**Example:**
```javascript
spUtil.addErrorMessage("Unable to save the record.");
```

---

### **3. `spUtil.addTrivialMessage(message)`**

**Definition:** Displays a low-priority message (less noticeable than info).

**Example:**
```javascript
spUtil.addTrivialMessage("Optional step completed.");
```

---

### **4. `spUtil.showModal(template, params)`**

**Definition:** Opens a modal (popup) using a specified widget template and passes parameters to it.

**Example:**
```javascript
spUtil.showModal('custom-modal-widget', {
  title: 'My Modal',
  user_id: 'abc123'
}).then(function(modal) {
  console.log("Modal was closed.");
});
```

---

### **5. `spUtil.hideModal()`**

**Definition:** Closes the currently open modal.

**Example:**
```javascript
spUtil.hideModal();
```

---

### **6. `spUtil.scrollTo(selector)`**

**Definition:** Smoothly scrolls the page to a specific element using a CSS selector.

**Example:**
```javascript
spUtil.scrollTo('#topFormSection');
```

---

### **7. `spUtil.setBreadCrumb(segments)`**

**Definition:** Sets the breadcrumb navigation at the top of a Service Portal page.

**Example:**
```javascript
spUtil.setBreadCrumb([
  { label: 'Home', url: '#!/' },
  { label: 'My Tickets', url: '#!/my-tickets' }
]);
```

---

### **8. `spUtil.updateUrl(params, options)`**

**Definition:** Updates the browser URL without reloading the page. Useful for SPA (single page app) behavior.

**Example:**
```javascript
spUtil.updateUrl({ id: 'ticket_view', sys_id: '1234' });
```

---

### **9. `spUtil.getURLParameters()`**

**Definition:** Returns all the current URL parameters as a key-value object.

**Example:**
```javascript
var params = spUtil.getURLParameters();
console.log(params.sys_id);  // e.g., "1234"
```

---

### **10. `spUtil.navigate(url)`**

**Definition:** Redirects the user to another URL within the Service Portal.

**Example:**
```javascript
spUtil.navigate('#!/catalog');
```

---

### **11. `spUtil.get(url, data)`**

**Definition:** Makes a GET request to a REST API or Script Include endpoint.

**Example:**
```javascript
spUtil.get('/api/now/table/incident', {}).then(function(response) {
  console.log(response.data);
});
```

---

### **12. `spUtil.post(url, data)`**

**Definition:** Sends a POST request to a REST API or custom endpoint.

**Example:**
```javascript
var payload = { short_description: "New incident" };
spUtil.post('/api/now/table/incident', payload).then(function(response) {
  console.log("Created Incident:", response.result);
});
```

---

### **13. `spUtil.recordWatch(table, sysId)`**

**Definition:** Sets up a **real-time watch** on a GlideRecord, so your widget updates when that record changes.

**Example:**
```javascript
spUtil.recordWatch('incident', '1234567890abcdef1234567890abcdef');
```

---

Let me know if you want a full working widget example using `spUtil` modals or API calls!
