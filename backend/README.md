Open the folder with project
```
cd kittygram_backend
```

Create and activate virtual environment:

```
python3 -m venv env
```

* If you use Linux/macOS

    ```
    source env/bin/activate
    ```

* If you use windows

    ```
    source env/scripts/activate
    ```

```
python3 -m pip install --upgrade pip
```

Install dependencies from requirements.txt:

```
pip install -r requirements.txt
```

Apply migrations:

```
python3 manage.py migrate
```

Run project:

```
python3 manage.py runserver
```
