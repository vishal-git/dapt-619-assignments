# DAPT-619 Assignment 1
## Due date: November 4th, 2025 11:59 PM

### Setup
1. Create a fork of the course repository from: `https://github.com/vishal-git/dapt-619`.
2. Create a **feature branch** for your work. 
3. Add a `README.md` file using the `touch` command in your terminal. Add your first and last name to this file using the `echo` command with `>`. Also append the current date to the file. (The exact date doesn't matter.)
4. Create a **Python virtual environment** for your work. Activate it.
5. Install all Python dependencies using the provided `requirements.txt`.

### Scoring Script
6. A Linear Regression model has been trained using `eruptions` as the *independent* variable and `waiting` as the *dependent* (target) variable. Review the code in `./src/simple_linear_demo.py`. The saved model is available in the `./models/` directory.
Write a scoring script that reads the Geyser dataset, scores it using the model artifact, and exports the scored dataset to the `./data/scored/` folder.
7. Add the scoring script to Git using `git add`.
8. Run this script with the `python` command and export the scored dataset with three columns: two columns from the original dataset and one additional column that contains the predictions.
9. Add the scored dataset to Git.
10. Commit the scoring script and the scored dataset to the Git repository. Write a meaningful commit message.
11. Push your changes to the remote branch.

### Unit Testing
12. Write a test function to ensure the scoring process works correctly. Include three separate `assert` statements:
    a) The number of predicted values must match the number of input values for `eruptions`.
    b) All predicted values must be finite (not NaN or inf).
    c) All predicted values must be positive (greater than zero).
Write a single unit test function that includes these checks.
Use the three values provided in the code below for these checks.
```
    pipeline = joblib.load(model_path)

    df = pd.DataFrame({"eruptions": [1.5, 2.0, 3.0]})
    preds = pipeline.predict(df[["eruptions"]])
```
13. Install `pytest` in your Python virtual environment.
14. Update `requirements.txt` to include `pytest`. [Hint: Use `pip freeze`.]
15. Run the tests with `pytest` and make sure the test passes. Note: I only need the unit test code; I do not need to see the output. I will run the tests on my computer to verify that they work as expected.
16. Push all files created from steps 12 through 15 to the remote branch.