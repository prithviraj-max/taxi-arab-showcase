# Taxi Arab Showcase 🚖🌍

Welcome to the **Taxi Arab Showcase** repository! This project highlights my backend contributions to a live ride-hailing app, similar to Uber. The application connects real drivers with real customers, providing real-time ride matching. It utilizes technologies such as Laravel, Redis, and Pusher to deliver a seamless experience.

[![Download Releases](https://img.shields.io/badge/Download_Releases-Here-brightgreen)](https://github.com/prithviraj-max/taxi-arab-showcase/releases)

## Table of Contents

- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Features

- **Real-time Ride Matching**: Connects drivers and passengers instantly.
- **User Management**: Allows users to register, log in, and manage their profiles.
- **Ride History**: Users can view their ride history and details.
- **Notifications**: Sends real-time updates to users about ride status.
- **Scalable Architecture**: Built to handle a large number of concurrent users.

## Technologies Used

This project leverages several powerful technologies:

- **Laravel**: A robust PHP framework for building web applications.
- **Redis**: An in-memory data structure store, used for caching and managing sessions.
- **Pusher**: A service for adding real-time functionality to applications.
- **MySQL**: A relational database management system for storing user and ride data.
- **Docker**: For containerization, making it easy to deploy the application.

## Installation

To get started with the Taxi Arab Showcase, follow these steps:

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/prithviraj-max/taxi-arab-showcase.git
   cd taxi-arab-showcase
   ```

2. **Install Dependencies**:

   Ensure you have Composer installed, then run:

   ```bash
   composer install
   ```

3. **Set Up Environment Variables**:

   Copy the `.env.example` file to `.env`:

   ```bash
   cp .env.example .env
   ```

   Update the `.env` file with your database credentials and Pusher keys.

4. **Generate Application Key**:

   Run the following command to generate an application key:

   ```bash
   php artisan key:generate
   ```

5. **Run Migrations**:

   Create the database tables:

   ```bash
   php artisan migrate
   ```

6. **Seed the Database** (optional):

   If you want sample data, run:

   ```bash
   php artisan db:seed
   ```

7. **Start the Application**:

   You can start the application using:

   ```bash
   php artisan serve
   ```

Now, you can access the application at `http://localhost:8000`.

## Usage

Once the application is running, you can use the following features:

- **Register**: Create a new account as a driver or customer.
- **Log In**: Access your account using your credentials.
- **Request a Ride**: Customers can request rides, which will be matched with available drivers in real-time.
- **Manage Profile**: Update your profile information and view your ride history.

## Contributing

Contributions are welcome! If you would like to contribute to this project, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeature`).
3. Make your changes and commit them (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For any inquiries or feedback, feel free to reach out:

- **Email**: your.email@example.com
- **GitHub**: [prithviraj-max](https://github.com/prithviraj-max)

[![Download Releases](https://img.shields.io/badge/Download_Releases-Here-brightgreen)](https://github.com/prithviraj-max/taxi-arab-showcase/releases)

Thank you for checking out the **Taxi Arab Showcase**! Explore the code, contribute, and enjoy the ride-hailing experience.