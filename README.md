# API and Database Design for HNG Boilerplate Project

## API Design

This project uses Swagger/OpenAPI to design the APIs. A minimal list of the API description is listed below: 

### API Base url: [here](link-to-swagger-documentation)

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


#### For detailed API specifications, refer to the [OpenAPI Specification](link-to-openapi-spec).

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


For a detailed view, you can access the draw.io file [here](https://drive.google.com/file/d/1bCSuJ6I8GPU-jEiOfVUcaau72-Tv2GRl/view?usp=sharing).
