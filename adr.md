# ADR: Architectural Decisions for Retail Mobile App

## Context
 Developing a mobile app for a retail company, offering customers the ability to browse, purchase products, view order history, and track deliveries. The app will also include a loyalty program. The following requirements need to be addressed and decisions need to be made in order to move forward with development.

- **Offline Mode**:
   - The app should support offline mode, this will allow customers to browse products and view their orders and history. In order for this to be possible, the application will sync data with the server when the user gains internet connection.

- **Push Notifications**:
   - The app must integrate with a push notification service to send notifications on orders, new products, and exclusive offers to customers in order to keep them up to date.

- **Payment Gateways**:
   - Various payment gateways need to be integrated to ensure that users can safely and conveniently make payments. The gateway selection should consider platform compatibility, security and usability.

- **Analytics**:
   - Tracking user behavior such as purchases, product views, and loyalty program interactions are essential for the application.  A tool or service that provides data analytics is required in order to gain insights for improvements.

- **Image Handling**:
   - Image storage, caching, lazy loading, and compression strategies must be chosen for optimal performance as the app will display images that may vary in size and/or resolution.

- **Localization**:
   - Regarding localization, the application needs to support multiple languages and cultural preferences to cater to an international audience. To achieve this, a localization framework or library should be implemented into the app.

### Key Decisions:

- **Offline Mode**:
   - Decision: Local data caching and synchronization will be implemented using a combination of local storage (e.g., SQLite for structured data) and a background sync service when internet connection is available for the user.
   - Rationale:
     - Local storage ensures seamless offline access.
     - Background synchronization ensures data consistency with the server.

- **Push Notifications**:
   - Decision: Firebase Cloud Messaging will be integrated for push notifications.
   - Rationale:
     - Firebase Cloud Messaging is built on Google's infrastructure which is known for it's reliability. It also supports real-time messaging.
     - Firebase is cross-platform which is essential for the application.
     - Firebase provides a user-friendly dashboard for managing notifications.
     - Firebase supports user segmentation which allows the app to send targeted notifications to users.  This is important for personalized and user-specific notifications.

- **Payment Gateways**:
   - Decision: We will integrate Stripe as the primary payment gateway, with secondary options like PayPal and Apple Pay.
   - Rationale:
     - Stripe offers strong security and ease of integration.
     - Stripe also supports up to 135 different currencies which is essential as it gives users further convenience during the payment process.
     - Supporting multiple gateways such as Apple Pay and PayPal further enhances customer payment flexibility.
     - Stripe offers tools for businesses to handle recurring and timed payments.  This can help to easily set up customer subscriptions and trial periods.

- **Analytics**:
   - Decision: Google Analytics will be used for tracking user behavior.
   - Rationale:
     - Google Analytics provides comprehensive tracking and analysis capabilities such as page views, events and e-commerce transactions.
     - Integration is straightforward and well-documented.
     - Google analytics provides robust filtering as well as funnels and user flow analysis which allows for deeper and more comprehensive data analysis.

- **Image Handling**:
   - Decision: Content Delivery Network (CDN) will be used for image storage and image optimization techniques, including caching, lazy loading, and server-side compression will be implemented.
   - Rationale:
     - A CDN ensures fast and reliable image delivery.
     - A CDN provides image optimization techniques improve app performance and reduce bandwidth usage.
     - A CDN also supports customizable image delivery, which allows for images to be defined based on user location and  device.

- **Localization**:
   - Decision: The react-i18next library will be used for app localization.
   - Rationale:
     - react-i18next is a widely-used and well-maintained and regularly updated library for handling localization.
     - It supports multiple languages and provides a straightforward way to manage translations.

## Status
Accepted

## Author
Yafiet Haile
Date: 2023-10-08