# Sudoku Solver

This is a Suoku solver written in Python. The algorithm uses MRV backtracking and comes with a user interface written in Flask.

by **Max Talberg**

## Using Docker to Run the Sudoku Solver

This application can be run in two modes using Docker: as a command-line tool to process a puzzle file or as a web application. Below are the instructions for both.

### Building the Docker Image

**Clone the Repository:**
   - First, clone the repository from GitLab:
     ```bash
     git clone git@gitlab.developers.cam.ac.uk:phy/data-intensive-science-mphil/c1_assessment/mt942.git
     ```

**Build the Docker Image:**
   - Build the Docker image:
     ```bash
     docker build -t sudoku-solver .
     ```
### Running the Command-Line Application with Docker

#### Internal files
**Run the Docker Container:**
   - Execute the following command in your terminal, to access internal data files contained in Docker:
     ```bash
     docker run -v /path/to/local/directory:/usr/src/app/data sudoku-solver data/input.txt
     ```
   - Files in the data directory include:
        - `empty_board.txt` - a sample empty board
        - `empty_file.txt` - a sample empty file
        - `input.txt` - a sample input board
        - `invalid_board.txt` - a sample invalid board
        - `invalid_character_board.txt` - a sample invalid character board
        - `invalid_column_board.txt` - a sample invalid column board
        - `invalid_row_board.txt` - a sample invalid row board
        - `invalid_size_board.txt` - a sample invalid size board
        - `invalid_square_board.txt` - a sample invalid square board
        - `less_than_17_board.txt` - a sample board with less thanm 17 clues
        - `slow_unsolvable_board.txt` - a sample unsolvable board
        - `solved_board.txt` - a sample solved board
        - `not_a_text_file.pdf` - a sample non-text file

#### External files
**Prepare Your Input File:**
   - Place the input file (e.g., `puzzle.txt`) in a known directory on your machine.

**Run the Docker Container:**
   - Execute the following command in your terminal, replacing `/path/to/local/directory` with the path to the directory containing your puzzle file:
     ```bash
     docker run -v /path/to/local/directory:/usr/src/app/data sudoku-solver data/puzzle.txt
     ```

### Running the Web Application with Docker

1. **Run the Docker Container for Web App:**
   - To run the web application, use the following command:
     ```bash
     docker run -p 8888:80 sudoku-solver --web
     ```

2. **Access the Web Application:**
   - Open a web browser and navigate to `http://localhost:8888`.
   - The user interface is invtuitive, uploading a file is performed by drag and drop or by clicking the upload button.

## Running the Sudoku Solver Locally

This section provides instructions on how to run the Sudoku Solver project directly on your local machine.

### Setting Up the Project

1. **Clone the Repository:**
   - Clone the repository from GitLab:
     ```bash
     git clone git@gitlab.developers.cam.ac.uk:phy/data-intensive-science-mphil/c1_assessment/mt942.git
     ```

2. **Set Up a Virtual Environment:**

     ```bash
     conda create --name sudoku_env python=3.8
     conda activate sudoku_env
     ```

3. **Install Dependencies:**

     ```bash
     conda env create -f environment.yml
     ```

### Running the Application

1. **Run the Command-Line Application:**
   - To solve a puzzle from a file:
     ```bash
     python src/solve_sudoku.py data/input.txt
     ```

2. **Run the Web Application Locally:**
   - If your project includes a web application:
     ```bash
     python src/solve_sudoku.py --web
     ```
   - Access the web application by navigating to `http://127.0.0.1:80` in your web browser.
### Notes

- This setup assumes the use of `conda` over `pip`.

## Documentation
### Docker
- When the Docker image for the Sudoku Solver is built, the project's Sphinx documentation is automatically built.

### Local
1. **Navigate to the `docs` directory:**
   - Navigate to the `docs` directory:
     ```bash
     cd docs
     ```
2. **Build the Documentation:**
    - Build the documentation:
      ```bash
      sphinx-build -b html . /path/to/output/directory
      ```
    - Replace `/path/to/output/directory` with the path where you want the built documentation to be placed.

## Testing

To run tests for the Sudoku Solver project, follow these steps:

### Running Unit Tests

- Before running tests, ensure that the Python path is set up correctly to include the project's source code. This can be done in several ways:

  1. **Modify PYTHONPATH:**
     ```bash
     export PYTHONPATH=$PYTHONPATH:/src
     ```

  2. **Run Unit Tests:**
     - Run the unit tests using:
       ```
       pystest
       ```


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

### Use of Generative Tools

This project has utilised GitHub Copilot for code completion and assistance with text prompts.

Although these tools aid the development process, its use was limited and only effective inscenarios where the developer had a clear idea of the code's structure and implementation.

For instance:
- Plotting of functions
- Implementation of Latex and README
- Auto-complete of docstrings