## Grand Iftar – MUIS Lookup System

This is a simple Django-based lookup system for **Grand Iftar – MUIS**.

### Features

- User enters an ID.
- Participant data is loaded from `data.txt`.
- If the ID matches, the system shows the full participant information.
- A **unique token** is generated per ID and stored permanently in `tokens.txt`.
- If a token was already generated for that ID, the **same token** is reused.
- Fully responsive, modern UI (Bootstrap-based).

### Data Files

- **`data.txt`**: Source of participant data.
  - Location: project root (same folder as `manage.py`).
  - Format: CSV with a header row.
  - Example:

    ```text
    id,name,group,seat
    12345,Ali Bin Ahmad,Family A,Table 3
    67890,Siti Binte Omar,Family B,Table 5
    ```

- **`tokens.txt`**: Persistent store of generated tokens.
  - Location: project root.
  - Format: CSV **without** a header row: `id,token,created_at`.
  - The system will create this file automatically if it does not exist.

### Quick Start

1. Create and activate a virtual environment (recommended).
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Run database migrations:

   ```bash
   python manage.py migrate
   ```

4. Start the development server:

   ```bash
   python manage.py runserver
   ```

5. Open `http://127.0.0.1:8000/` and use the Grand Iftar lookup page.

### Customisation

- Edit `data.txt` with your real participant data.
- The UI is built with Bootstrap 5; you can customise the template in `iftar/templates/iftar/index.html`.
