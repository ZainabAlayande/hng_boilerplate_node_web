# API and Database Design for HNG Boilerplate Project

## API Design

This project uses Swagger/OpenAPI to design the APIs. A minimal list of the API description is listed below: 

### API Base url

 - Main Server [https://example.com/api/v1](link-to-swagger-documentation)
 - Staging Server [https://staging.example.com/api/v1]


### Endpoints

- **POST /auth/register**: Create a new user.
- **POST /auth/login**: Login a user.
- **POST /auth/social**: Create new user by social authentication.
- **POST /auth/magic-link**: Magic link login.
- **POST /auth/change-password**: Change user password
- **POST /email/send**: Send a mail to user
- **POST /payments/stripe**: Process a Stripe Payment
- **POST /payments/flutterwave**: Process a Flutterwave payment
- **POST /payments/lemonsqueezy**: Process a LemonSqueezy payment
- **GET /users**: Get a list of users
- **GET /users/{id}**: Get user by ID


#### For detailed API specifications, refer to the [OpenAPI Specification](https://app.swaggerhub.com/apis/ZainabAlayande/boilerplate-api/1.0.0).

## Database Design

The database design is created using draw.io. The Entity Relation Diagram can be viewed below:


### Entities

A quick view of the boilerplate entity/model is extracted below

- **Users**
- **Organization**
- **Superadmin**
- **Payment**
- **PaymentMethod**
- **PaymentStatus**
- **BlogPost**
- **ActivityLog**
- **Message**
- **BlogPost**
- **Invite**
- **Notification**

 

### Relationships

- Users and Organizations:

  - One User can belong to multiple Organizations.
  - One Organization can have many Users.

- Users and Superadmin:

  - Users can have roles that grant them Superadmin   privileges.
  - Superadmins oversee Users and Organizations.

- Organization and Payments:

  - An Organization can initiate Payments for services rendered.
  -- Payments are associated with specific Organizations.

- Users and Messages:

  - Users can send and receive Messages within the platform.
  - Messages are linked to specific Users.

- Organization and Blog Posts:

  - Organizations can publish Blog Posts to communicate updates or insights.
  - Blog Posts are attributed to the publishing Organization.

- Superadmin and Activity Log:

  - Superadmins have access to the Activity Log, documenting user and system actions.
  - Activity Logs provide transparency and oversight for Superadmins.

- Users and Invites:

  - Users can generate Invites to invite others to join the platform.
  - Invites track the status and recipients of invitations.

- Users and Notifications:

  - Users receive Notifications for important events or updates.
  - Notifications are triggered by system events related to Users' activities.

- Payment and Payment Methods:

  - Payments can be made using various Payment Methods (e.g., Stripe, PayPal).
  - Payment Methods specify how transactions are processed.

- Payment and Payment Status:

  - Payments have statuses indicating whether they are pending, completed, or failed.
  - Payment Status updates reflect the current state of financial transactions.


For a detailed view, you can access the draw.io file [here](https://viewer.diagrams.net/index.html?tags=%7B%7D&lightbox=1&highlight=0000ff&edit=_blank&layers=1&nav=1&title=Team-superstar.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1bCSuJ6I8GPU-jEiOfVUcaau72-Tv2GRl%26export%3Ddownload#%7B%22pageId%22%3A%22R2lEEEUBdFMjLlhIrx00%22%7D).
