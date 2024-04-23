# Inventaario
Inventaario

Mockup
<img src="https://raw.githubusercontent.com/GreySkySpin/Inventaario/main/Ty%C3%B6kalut%20-%20L%C3%B6yt%C3%A4%C3%A4.png" height="100%">

====== Development Plan ======

===== ENGLISH VERSION =====

AIM: To make a QR-code generator to generate qr codes from a wiki: https://wiki.tampere.hacklab.fi/

**Schema and implement security features**

Schema and implement security features to ensure the confidentiality of contact information:

1. Tables:

  Contacts Table
  Fields:
  * ContactID (Primary Key)
  * Name
  * Email
  * Phone
  * Expertise (e.g., electronics, woodworking)

  Tools Table
  Fields:
  * ToolID (Primary Key)
  * Name
  * Description
  * Category
  * Quantity
  * Location
  * Condition (e.g., new, used)
  * Availability (e.g., available, checked out)

  QR Codes Table:
  Fields:
  * QRCodeID (Primary Key)
  * ToolID (Foreign Key referencing Tools)
  * Link
  * CreationTimestamp

2. Website Contact Form

  * Implement a contact form on your website where users can submit inquiries or requests to contact specific individuals.
  * When a user submits the form, the website backend will handle the request and forward it to the appropriate contact without revealing their email address or phone number.

3. Security Measures

  * Encryption: Encrypt sensitive data (such as email addresses and phone numbers) in the database to prevent unauthorized access.
  * Access Control: Implement access controls to restrict access to contact information only to authorized users with appropriate permissions.
  * Authentication: Require users to authenticate before accessing any contact information or using the contact form.
  * Secure Communication: Ensure that communication between the website and the server is encrypted using HTTPS to prevent interception of sensitive data.

By implementing these security measures, you can protect the privacy of contact information while still facilitating communication between users and contacts through the website. Users can submit inquiries or requests without directly accessing contact details, maintaining confidentiality and security.

**Tech Stack**

Development stack tailored to using PostgreSQL and Hacklab's server:

1. Frontend Framework: FlutterFlutter will be used for building the mobile and web frontend of your application. Flutter's single codebase can target multiple platforms, ensuring consistency across mobile devices and web browsers. 
2. Backend Framework: Django
   Django will serve as the backend framework for your application, providing RESTful APIs to communicate with the Flutter frontend. Django's robust features, including authentication, ORM (Object-Relational Mapping), and built-in admin interface, make it well-suited for building backend services. 
3. Database: PostgreSQL
   PostgreSQL remains the chosen database management system for storing structured data such as tools, contacts, and QR code information. Django has excellent support for PostgreSQL through its ORM, allowing seamless integration with the backend. 
4. Authentication and Security: Django Authentication
   Django provides built-in authentication and authorization features, including user authentication, permissions, and session management. You can leverage Django's authentication system to secure your backend APIs and user data. 
5. Integration with Brother P-touch Cube Printer: Brother Mobile SDK
   Integrate the Brother Mobile SDK with your Flutter application for printing QR codes using the Brother P-touch Cube printer, as previously discussed. The integration will be handled primarily on the frontend side, with Flutter communicating with the printer SDK.
6. Deployment: Deployment to Cloud Platform
   Deploy your Django backend and Flutter frontend to a cloud platform such as AWS (Amazon Web Services), Google Cloud Platform, or Heroku. These platforms offer scalable infrastructure, managed services, and easy deployment options for both backend and frontend components.

By using this development stack, you can leverage PostgreSQL's robustness and reliability for storing your application's data while utilizing Flutter and Django for frontend and backend development, respectively. This stack provides a solid foundation for building a secure, scalable, and efficient web application tailored to Hacklab's requirements.

By adopting Django as the backend framework alongside Flutter for frontend development, you can build a full-stack application with a modern and scalable architecture. Django's rich ecosystem of libraries and tools, combined with Flutter's cross-platform capabilities, enables you to develop and deploy a feature-rich application efficiently.

**Mobile First**

Given that your web application will primarily be accessed by users at the Hacklab and you want to prioritize mobile accessibility, adopting a "mobile-first" approach makes sense. This means designing and developing the web application with the mobile user experience as the primary focus, ensuring that it is optimized for smaller screens and touch interactions.

Here are some considerations for implementing a mobile-first approach:

1. Responsive Design: Design your user interface to adapt seamlessly to various screen sizes, from smartphones to tablets and desktops. Utilize CSS media queries and flexible layout techniques to ensure that content is displayed appropriately across different devices.

2. Touch-Friendly Interactions: Optimize user interactions for touch-based input, such as swiping, tapping, and gestures. Ensure that buttons and other interactive elements are adequately sized and spaced to accommodate finger taps.

3. Performance Optimisation: Mobile devices may have limited processing power and network bandwidth compared to desktops. Optimise your web application for performance by minimizing load times, reducing unnecessary animations and scripts, and employing techniques like lazy loading for images and content.

4. Progressive Web App (PWA) Features: Consider implementing PWA features such as offline caching, push notifications, and home screen installation to enhance the mobile user experience further. PWAs can provide a more app-like experience for users accessing your web application on mobile devices.

5. Cross-Platform Compatibility: Ensure that your web application is compatible with various mobile browsers and operating systems, including iOS and Android. Test your application thoroughly on different mobile devices to identify and address any compatibility issues.

Regarding printing QR codes, your approach of having a printer connected to a computer (or network) for automatic printing or manually sending image files to the printer can work well. You may need to integrate your web application with a printing solution or service to facilitate the generation and printing of QR codes directly from the application.

By adopting a mobile-first approach and considering the printing requirements, you can create a web application that provides a seamless and optimized experience for users accessing the database from mobile devices while accommodating additional functionalities like QR code printing.

**Printing QR Code Labels**

With the Android Labeling and Mobile SDK provided by Brother, you can integrate the Brother P-touch Cube label printer with your Android mobile application for printing QR codes.

https://developerprogram.brother-usa.com/sdk-download

Here's how you can proceed with the integration:

1. Download and Install the SDK:

  - Download the Android Labeling and Mobile SDK from the provided link.
  - Follow the installation instructions and setup process outlined in the SDK documentation.

2. Explore SDK Documentation:

  - Familiarize yourself with the documentation provided with the SDK. It should include information on APIs, usage examples, and best practices for integrating with Brother label printers.

3. Integrate SDK with Your Android Application:

  - Add the Brother Mobile SDK to your Android project by including the necessary dependencies and configurations.
  - Set up your Android application to communicate with the Brother P-touch Cube printer using the SDK.
  - Utilize the SDK's APIs to send print commands and data to the printer from your Android application.

4. Generate QR Codes Dynamically:

  - Implement logic within your Android application to generate QR codes dynamically based on user input or database queries.
  - Use a QR code generation library compatible with Android, such as ZXing (Zebra Crossing), to generate QR code images programmatically.

5. Handle User Interaction:

  - Create a user interface in your Android application for triggering QR code printing.
  - When a user initiates a print action, invoke the necessary SDK methods to generate the QR code image and initiate printing on the Brother P-touch Cube printer.

6. Printer Configuration:

  - Ensure that the Brother P-touch Cube printer is connected to the Android device via Bluetooth or another compatible connection method.
  - Configure the printer settings, such as label size, orientation, and printing options, as needed for your QR code labels.

7. Testing and Debugging:

  - Test the integration thoroughly to ensure that QR codes are generated accurately and printed correctly by the Brother P-touch Cube printer.
  - Debug any issues that arise during integration, such as connectivity problems or formatting errors.

8. Documentation and Support:

  - Refer to the SDK documentation and resources provided by Brother for troubleshooting, best practices, and additional guidance during the integration process.
  - Reach out to Brother's developer support team if you encounter any challenges or require assistance with specific aspects of the integration.

By following these steps and leveraging the capabilities of the Android Labeling and Mobile SDK provided by Brother, you can seamlessly integrate the Brother P-touch Cube label printer with your Android mobile application to enable users to generate and print QR codes for labeling tools and equipment at the Hacklab.


Other relevant links:

https://wiki.tampere.hacklab.fi/qr-codes/thln0001


