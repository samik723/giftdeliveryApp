# Gift Delivery Application

## Table of Contents
- [Introduction](#introduction)
- [Database Creation](#database-creation)
- [API Testing](#api-testing)
- [User Acceptance Testing](#user-acceptance-testing)
- [Test Plan](#test-plan)
- [Test Outcomes](#test-outcomes)
- [Features Successfully Implemented](#features-successfully-implemented)
- [Features Not Successfully Implemented](#features-not-successfully-implemented)
- [Conclusion](#conclusion)

---

## Introduction

The Gift Delivery Application project is designed to provide a user-friendly platform for ordering and managing gift deliveries. Developed using **Node.js**, **Express.js**, **MongoDB**, and **Cordova**, the app integrates a cloud-hosted database and hybrid deployment for web and Android platforms.

---

## Database Creation

Screenshots of database creation in MongoDB Atlas.

### Populating the Collections in MongoDB Atlas

- **Users Collection**  
  ![Users Collection](assets/users-collection.png)

- **Orders Collection**  
  ![Orders Collection](assets/orders-collection.png)

---

## API Testing

The connection string was replaced with: mongodb+srv://samiknj34:samik123@cluster0.ww15q.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0
The app was successfully connected to MongoDB Atlas.

Tested API endpoints using **Postman**:

- `http://localhost:3000/getUserDataTest`
- `http://localhost:3000/getOrderDataTest`

---

## User Acceptance Testing

### Test Plan

| Test Scenario                        | Test Case Description                                    | Expected Outcome                                          | Actual Outcome                                          | Status |
|-------------------------------------|----------------------------------------------------------|-----------------------------------------------------------|----------------------------------------------------------|--------|
| User Registration                   | Register with valid data                                 | User registered and redirected to login page              | Success                                                  | ✅ Pass |
| Invalid Email Format on Registration| Use invalid email format                                 | Error: "The email format is incorrect."                   | Error displayed                                          | ✅ Pass |
| Missing Required Fields             | Leave required fields blank                              | Error messages for blank fields                           | Errors displayed as expected                            | ✅ Pass |
| Login with Valid Credentials        | Use correct email & password                             | Login successful and redirect                             | Success                                                  | ✅ Pass |
| Login with Invalid Credentials      | Use wrong email/password                                 | Error: "Incorrect email or password."                     | Error shown                                              | ✅ Pass |
| Place Order                         | Submit valid order                                       | Order placed and confirmation shown                       | Order saved and confirmed                               | ✅ Pass |
| View Past Orders                    | View previous orders                                     | Orders listed accurately                                  | Displayed correctly                                     | ✅ Pass |
| No Past Orders                      | Check with empty order history                           | Message: "No past orders found."                          | Message displayed                                        | ✅ Pass |
| Delete Orders                       | Delete selected past orders                              | Orders deleted, confirmation shown                        | Orders deleted successfully                             | ✅ Pass |
| Delete Orders Page Display          | View only logged-in user’s orders                        | Correct user orders displayed                             | Correct orders shown                                    | ✅ Pass |

---

## Test Outcomes

### Screenshots

- **User Registration**  
  ![User Registration](assets/user-registration.png)

- **Invalid Email Format on Registration**  
  ![Invalid Email Format](assets/invalid-email-format.png)

- **Missing Required Fields**  
  ![Missing Fields](assets/missing-required-fields.png)

- **Login with Invalid Credentials**  
  ![Invalid Login](assets/login-invalid.png)

- **Login with Valid Credentials**  
  ![Valid Login](assets/login-valid.png)

- **Placing Order**  
  ![Place Order](assets/place-order.png)

- **Update in Database**  
  ![Database Update](assets/database-update.png)

- **Past Order List**  
  ![Past Orders](assets/past-orders.png)

- **Delete Order Page**  
  ![Delete Page](assets/delete-order.png)

- **Delete Confirmation Page**  
  ![Delete Confirmation](assets/delete-confirmation.png)

*Console output from the Express server confirms all operations and data flow between client and server.*

---

## Features Successfully Implemented

1. **User Login and Registration**
   - `POST /registerUser`: Adds users with duplicate email check.
   - `POST /verifyUser`: Verifies user credentials.
   - jQuery form validation for both login and registration.

2. **Order Placement**
   - `POST /placeOrder`: Places new orders.
   - Input validation via jQuery, followed by redirection to confirmation page.

3. **Order Confirmation Page**
   - Order details shown dynamically using jQuery + AJAX from MongoDB.

4. **View Past Orders**
   - `POST /getUserOrders`: Fetches all user-specific orders.
   - Displayed with user-friendly formatting using jQuery.

5. **Delete Orders**
   - `DELETE /deleteUserOrders`: Deletes selected user orders.
   - Orders selected with checkboxes, then deleted with confirmation message.

6. **Hybrid App with Cordova**
   - Web + Android setup via Cordova environment.
   - Ensures smooth front-end compatibility on both platforms.

7. **Cloud Database Integration**
   - MongoDB Atlas used as a cloud-hosted, scalable NoSQL database.

---

## Features Not Successfully Implemented

1. **Android Emulator Testing**
   - The app sometimes crashes or lags when running on Android emulator.
   - Performance testing was not fully successful on emulated devices.

---

## Conclusion

In conclusion, the development of the Gift Delivery App (version 2) successfully implemented user authentication, order placement, database connectivity, and hybrid deployment. Despite some emulator testing issues, the core functionality and UX are solid across both web and mobile platforms.
