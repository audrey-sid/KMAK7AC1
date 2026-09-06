local_python <- file.path(getwd(), ".venv", "bin", "python")

if (file.exists(local_python)) {
  Sys.setenv(RETICULATE_PYTHON = local_python)
} else if (!nzchar(Sys.getenv("RETICULATE_PYTHON"))) {
  Sys.unsetenv("RETICULATE_PYTHON")
}

source(file.path(getwd(), "R", "functions.R"))