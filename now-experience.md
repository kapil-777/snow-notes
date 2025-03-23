## Core Concepts:

1. **Experience**  
   An experience is the web interface a user interacts with to use an application.

2. **Creating an Experience in Studio**  
   To create an experience in Studio, you need two records:
   - **UX Application record**  
   - **UX App Configuration record**  
   Experiences can have one or more pages for users to interact with the application.

3. **Editing an Experience in UI Builder**  
   You can open and edit an experience in UI Builder from the **UX App Configuration record** in Studio.
   
   ### UI Builder Sections (Visible by default):
   1. **Icon bar**
   2. **Header**
   3. **Page panel**
   4. **Stage**
   5. **Configuration panel**

## Page Creation:

1. **Building Pages**  
   Pages can either be:
   - **Built from scratch**
   - **Based on a template**
   
2. **Template Types**  
   - **Referenced Templates**:
     - Limited configuration options.
     - Updates automatically when the template is updated.
   - **Copied Templates**:
     - Completely configurable but disconnected from the original template once copied.

## Passing Parameters to a Page:

1. **Required Parameters**:  
   Must be passed and are appended to the page URL in a specific order.

2. **Optional Parameters**:  
   Can be passed if available, appended to the URL in property/value pairs.

3. **Context Props Object**:  
   Look for references to the `context.props` object in the template page's component settings to identify which parameters need to be passed.

## Components and Layout:

1. **Page Components**:  
   Pages are built using **components**.

2. **Container Components**:  
   Used to lay out a page. Containers organize other components.

3. **Non-container Components**:  
   Add content and interactivity to a page.

4. **Component Organization**:  
   Components are placed inside containers, which can be organized into rows or columns.

5. **Customization**:  
   Configuration options and CSS are used to adjust the look and feel of components.

## Visual Elements:

1. **Adding Images**:  
   You can add images to the application for visual appeal and to enhance the user experience.

## Page Variants:

1. **Variants**:  
   **Page variants** allow the same URL to show different content based on certain conditions.

2. **Audience**:  
   Variants use a targeted group of users (called an **audience**) to decide which variant is shown.
