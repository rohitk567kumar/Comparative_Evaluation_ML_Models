# Data conventions

- `raw/` contains downloaded UCI archives and files extracted from those archives.
  Original downloads are immutable inputs and must not be edited.
- `interim/` is for derived, inspectable intermediate artifacts.
- `processed/` is reserved for future experiment inputs.
- Every derived data product should document its source file, transformation, and
  generation command.
