# Health Application

A full-stack health management application built with React and Node.js that allows users to track their health metrics, manage appointments, store medical records, and access emergency services.

## Features

- **Authentication**: Secure login and registration system
  - User login with email/password
  - New user registration
  - Protected routes requiring authentication
  - User profile display with logout functionality
- **Dashboard**: Overview of health metrics and upcoming appointments with quick actions
  - Book appointments directly from dashboard
  - Add health records with modal form
  - Navigate to reports
  - Emergency quick access buttons
- **Health Metrics**: Track heart rate, blood pressure, weight, and daily steps
- **Appointments**: Schedule and manage medical appointments with full CRUD operations
- **Medical Records**: Upload and manage medical documents
- **Reports**: Generate and view comprehensive health reports
  - Summary statistics
  - Custom date range reports
  - Download reports in PDF/Excel format
  - Health trends visualization
- **Emergency Services**: Critical emergency features
  - Ambulance booking with GPS location tracking
  - Emergency contact numbers (911, 108, 100, 101, Poison Control)
  - Real-time tracking with booking ID and ETA
- **First Aid Guide**: Comprehensive searchable first aid library
  - CPR instructions
  - Choking procedures
  - Bleeding control
  - Burn treatment
  - Fracture management
  - Poisoning response
  - Heart attack response
  - Stroke recognition and response
- **User Profile**: Manage personal and medical information

## Tech Stack

### Frontend
- React 18
- React Router (for navigation)
- Axios (for API calls)
- React Icons (for UI icons)
- Chart.js (for data visualization)

### Backend
- Node.js
- Express.js
- Multer (for file uploads)
- CORS (for cross-origin requests)

## Project Structure

```
test-prj/
├── client/                 # React frontend
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/    # Reusable components
│   │   │   ├── Navbar.js
│   │   │   ├── Navbar.css
│   │   │   ├── Sidebar.js
│   │   │   ├── Sidebar.css
│   │   │   ├── Login.js
│   │   │   ├── Login.css
│   │   │   ├── BookAppointmentModal.js
│   │   │   ├── BookAppointmentModal.css
│   │   │   ├── AddHealthRecordModal.js
│   │   │   └── AddHealthRecordModal.css
│   │   ├── context/       # React Context
│   │   │   └── AuthContext.js
│   │   ├── pages/         # Page components
│   │   │   ├── Dashboard.js
│   │   │   ├── Dashboard.css
│   │   │   ├── HealthMetrics.js
│   │   │   ├── HealthMetrics.css
│   │   │   ├── Appointments.js
│   │   │   ├── Appointments.css
│   │   │   ├── MedicalRecords.js
│   │   │   ├── MedicalRecords.css
│   │   │   ├── Reports.js
│   │   │   ├── Reports.css
│   │   │   ├── Emergency.js
│   │   │   ├── Emergency.css
│   │   │   ├── FirstAid.js
│   │   │   ├── FirstAid.css
│   │   │   ├── Profile.js
│   │   │   └── Profile.css
│   │   ├── App.js
│   │   ├── App.css
│   │   ├── index.js
│   │   └── index.css
│   └── package.json
│
└── server/                # Node.js backend
    ├── routes/            # API routes
    │   ├── auth.js
    │   ├── dashboard.js
    │   ├── healthMetrics.js
    │   ├── appointments.js
    │   ├── medicalRecords.js
    │   ├── reports.js
    │   ├── emergency.js
    │   └── profile.js
    ├── server.js          # Main server file
    ├── .env              # Environment variables
    └── package.json
```

## Installation & Setup

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn

### Backend Setup

1. Navigate to the server directory:
```bash
cd server
```

2. Install dependencies:
```bash
npm install
```

3. Create uploads directory:
```bash
mkdir uploads
```

4. Start the server:
```bash
npm run dev
```

The server will start on `http://localhost:5000`

### Frontend Setup

1. Open a new terminal and navigate to the client directory:
```bash
cd client
```

2. Install dependencies:
```bash
npm install
```

3. Start the React development server:
```bash
npm start
```

The application will open in your browser at `http://localhost:3000`

## API Endpoints

### Authentication
- `POST /api/auth/login` - User login
- `POST /api/auth/register` - New user registration
- `POST /api/auth/logout` - User logout
- `GET /api/auth/verify` - Verify authentication token
- `GET /api/auth/me` - Get current user info

### Dashboard
- `GET /api/dashboard` - Get dashboard data

### Health Metrics
- `GET /api/health-metrics` - Get all health metrics
- `POST /api/health-metrics` - Add new health metric
- `DELETE /api/health-metrics/:id` - Delete a health metric

### Appointments
- `GET /api/appointments` - Get all appointments
- `POST /api/appointments` - Create new appointment
- `PUT /api/appointments/:id` - Update appointment
- `DELETE /api/appointments/:id` - Delete appointment

### Medical Records
- `GET /api/medical-records` - Get all medical records
- `POST /api/medical-records` - Upload new medical record (with file)
- `DELETE /api/medical-records/:id` - Delete medical record

### Profile
- `GET /api/profile` - Get user profile
- `PUT /api/profile` - Update user profile

### Reports
- `GET /api/reports` - Get health reports and statistics
- `POST /api/reports/generate` - Generate custom report with date range
- `GET /api/reports/download/:reportId` - Download generated report

### Emergency
- `POST /api/emergency/ambulance` - Book ambulance
- `GET /api/emergency/bookings` - Get all ambulance bookings
- `GET /api/emergency/track/:bookingId` - Track ambulance booking
- `PUT /api/emergency/bookings/:bookingId` - Update booking status
- `POST /api/emergency/log` - Log emergency call

## Features in Detail

### Authentication
- Secure login page with email and password
- New user registration with validation
- Password confirmation for registration
- Token-based authentication using localStorage
- Protected routes that redirect to login
- User profile display in navbar
- Logout functionality with confirmation
- Demo account credentials provided for testing
  - Email: demo@healthcare.com
  - Password: demo123

### Dashboard
- Quick overview of latest health metrics (heart rate, blood pressure, weight, temperature)
- List of upcoming appointments
- Emergency quick access buttons:
  - **Call Ambulance**: Navigate to ambulance booking
  - **First Aid**: Access first aid guides
- Quick action buttons with modals:
  - **Book Appointment**: Opens modal to schedule new appointment
  - **Add Health Record**: Opens modal to add new health metrics
  - **View Reports**: Navigate to reports page

### Health Metrics
- Add and track various health metrics
- View historical data in a table format
- Support for heart rate, blood pressure, weight, temperature, and step count
- Add records via Dashboard or Health Metrics page

### Appointments
- Book new appointments with doctors
- View all scheduled appointments
- Edit or cancel appointments
- Status tracking (confirmed/pending)

### Medical Records
- Upload medical documents (PDF, images)
- Categorize records by type (Lab Report, Imaging, Prescription, Report)
- View and download records
- Track document metadata (date, doctor, size)

### Profile Management
- Update personal information (name, email, phone, etc.)
- Manage medical information (blood group, allergies, chronic conditions)
- Emergency contact information

### Reports
- View comprehensive health statistics
- Generate custom reports with date range selection
- Download reports in PDF or Excel format
- View health trends and patterns
- Summary cards showing:
  - Total appointments (completed/upcoming)
  - Medical records count
  - Average health metrics
- Recent metrics table with status indicators
- Visual trend charts for heart rate and weight

### Emergency Services
- **Ambulance Booking**:
  - Patient information form
  - Emergency address input
  - GPS location capture (automatic)
  - Emergency type selection (Medical/Accident/Cardiac/Other)
  - Receive booking confirmation with ID and ETA
  - Track ambulance status
- **Emergency Contacts**:
  - Quick access to emergency numbers
  - 911 (Emergency Services)
  - 108 (Ambulance - India)
  - 100 (Police)
  - 101 (Fire Department)
  - 1-800-222-1222 (Poison Control)

### First Aid Guide
- Searchable library of 8 comprehensive first aid guides
- Filter by category
- Detailed step-by-step instructions
- Important warnings and cautions
- Covers:
  - CPR (Cardiopulmonary Resuscitation)
  - Choking procedures (Heimlich Maneuver)
  - Severe bleeding control
  - Burn treatment (1st, 2nd, 3rd degree)
  - Fracture stabilization
  - Poisoning response
  - Heart attack recognition and response
  - Stroke identification (FAST method) and response

## Current Implementation

This is a **mock data implementation** suitable for development and demonstration. The backend currently uses in-memory storage (arrays) for data persistence. The authentication system uses mock tokens and localStorage. For production use, you should:

1. Integrate a database (MongoDB, PostgreSQL, etc.)
2. Implement proper JWT authentication with refresh tokens
3. Add password hashing (bcrypt)
4. Add proper file storage (AWS S3, Google Cloud Storage, etc.)
5. Implement data validation and sanitization
6. Add error logging and monitoring
7. Implement proper security measures (HTTPS, rate limiting, CSRF protection, etc.)
8. Add email verification for registration
9. Implement password reset functionality
10. Add role-based access control (RBAC)

## Getting Started

1. **First Time Setup**: Complete both backend and frontend setup (see Installation & Setup section)
2. **Start Backend**: Navigate to `server/` and run `npm run dev`
3. **Start Frontend**: Navigate to `client/` and run `npm start`
4. **Login**: Use demo credentials:
   - Email: `demo@healthcare.com`
   - Password: `demo123`
5. **Or Register**: Create a new account through the registration form

## Future Enhancements

- Enhanced authentication (JWT with refresh tokens, OAuth integration)
- Two-factor authentication (2FA)
- Database integration (MongoDB/PostgreSQL)
- Real-time notifications using WebSockets
- Email/SMS notifications for appointments
- Prescription management and refill reminders
- Health goals tracking and reminders
- Telemedicine video consultations
- Integration with wearable devices (Fitbit, Apple Watch)
- AI-powered health insights and recommendations
- Multi-language support
- Dark mode
- Progressive Web App (PWA) capabilities
- Export health data to PDF/CSV
- Share reports with doctors
- Medication tracking and interactions checker
- Diet and nutrition tracking
- Exercise and fitness integration
- Mental health tracking

## Development

### Client Development
```bash
cd client
npm start
```

### Server Development
```bash
cd server
npm run dev
```

## Building for Production

### Build Frontend
```bash
cd client
npm run build
```

### Deploy Backend
Set up environment variables and deploy to your preferred hosting service (Heroku, AWS, DigitalOcean, etc.)

## License

MIT License

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## Support

For support, email support@healthapp.com or open an issue in the repository.
