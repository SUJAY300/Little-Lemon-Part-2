# Little Lemon Booking API — Course 7, Module 5, Lab 2

This ZIP is based on the provided Coursera starter project and implements the booking form and reservations JSON display.

## Included changes
- Added `restaurant/forms.py` with `BookingForm` based on the `Booking` model.
- Enabled the `book` and `bookings` views and app routes.
- Booking submissions are validated and saved through the Django model form.
- The reservations page serializes saved `Booking` objects to JSON and displays formatted JSON.
- Added the requested headings, date input behavior, and navigation links.

## Before running
1. Extract the ZIP and open the project root (the folder containing `manage.py`) in VS Code.
2. Ensure MySQL Server is running and the `reservations` database exists.
3. Open `littlelemon/settings.py` and update `DATABASES` `USER`, `PASSWORD`, `HOST`, and `PORT` to match your local MySQL setup. The starter settings use database `reservations`, user `root`, and password `root@123`; those credentials may not match your machine.
4. Activate/install dependencies with Pipenv:
   ```bash
   pipenv install
   pipenv shell
   ```
   If the shell command is unavailable in your Pipenv version, use `pipenv run` before Django commands.
5. Run:
   ```bash
   python manage.py makemigrations restaurant
   python manage.py migrate
   python manage.py check
   python manage.py runserver
   ```
6. Visit `/book/` to submit bookings and `/bookings/` to view stored reservations as formatted JSON.

## Notes
- Do not use the example database password in a production environment.
- The `date` query parameter is read in the `bookings` view as described in the lab; the lab instructions specify serializing all Booking objects.
- Booking records are stored in whichever database is configured in `settings.py`.
