# MedCenter - Clinic Management System

Course: Advanced Databases (NoSQL)
Group: BDA-2403
Authors:
* Kuandyk Bibarys
* Tulebai Aslan

## Project Description

MedCenter is a full-stack web application designed to manage clinical operations. It demonstrates advanced NoSQL database modeling techniques using MongoDB. The system facilitates patient-doctor interactions, appointment scheduling, and administrative analytics.

## Features

### Patient Module
* Authentication: Secure registration and login using JWT (JSON Web Tokens).
* Doctor Catalog: View a list of available specialists.
* Appointment Booking: Schedule appointments with doctors.
* Dashboard: Manage current and past appointments.
* Medical History: View personal medical records (Implementation of Embedded Documents).

### Admin Module
* Role-Based Access Control: Restricted access for administrators.
* Doctor Management: Add new doctors to the system.
* Analytics: View statistics on top-performing doctors (Implementation of Aggregation Framework).

## Technology Stack

* Database: MongoDB Atlas (Cloud)
* Backend: Node.js, Express.js
* Frontend: HTML5, CSS3 (Bootstrap 5), Vanilla JavaScript
* Authentication: bcryptjs (hashing), jsonwebtoken (sessions)
* Configuration: dotenv

## Database Architecture

This project fulfills the course requirements by implementing a hybrid data model:

1. Embedded Data Model:
   * Usage: User.medicalHistory
   * Justification: Medical history is strictly bound to a specific patient and is frequently read together with the user profile. Embedding reduces read latency.

2. Referenced Data Model (Normalization):
   * Usage: Appointment.patient and Appointment.doctor
   * Justification: Appointments and Doctors are independent entities. References allow the system to scale without hitting the MongoDB BSON document size limit.

3. Aggregation Framework:
   * Usage: Admin Statistics endpoint.
   * Pipeline: Utilizes $match, $group, $lookup, $sort, and $project stages to calculate business metrics on the server side.

## Installation and Setup

Follow these steps to run the project locally.

### 1. Prerequisites
* Node.js (v14 or higher) installed.
* An active MongoDB Atlas connection string.

### 2. Backend Setup
Navigate to the backend directory and install dependencies:

```bash
cd backend
npm install
