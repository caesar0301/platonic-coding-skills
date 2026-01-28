# Initialize Specs Folder

## Objective

Initialize a new specs folder with project-specific RFC templates, replacing `{{PROJECT_NAME}}` placeholders with the actual project name.

## Inputs

- **Project Name**: The name of the project (e.g., "MyProject")
- **Specs Directory**: Path to the specs directory (e.g., "./specs" or "/path/to/specs")

## Steps

1. **Create specs directory** if it doesn't exist
2. **Read template files** from `assets/` directory:
   - `rfc-standard.md.template`
   - `rfc-history.md.template`
   - `rfc-index.md.template`
   - `rfc-namings.md.template`
3. **Replace placeholders** in each template:
   - Replace `{{PROJECT_NAME}}` with the provided project name
   - Replace `YYYY-MM-DD` with today's date (format: YYYY-MM-DD)
4. **Write output files** to the specs directory:
   - `rfc-standard.md`
   - `rfc-history.md`
   - `rfc-index.md`
   - `rfc-namings.md`
5. **Verify** all files were created successfully

## Template Processing Rules

- **{{PROJECT_NAME}}**: Replace with the exact project name provided (case-sensitive)
- **YYYY-MM-DD**: Replace with current date in YYYY-MM-DD format
- **Preserve all other content** exactly as in templates
- **Maintain markdown formatting** and structure

## Output Files

After initialization, the specs directory should contain:

- `rfc-standard.md` - RFC specifications and management guide
- `rfc-history.md` - Change history template (ready for events)
- `rfc-index.md` - RFC index template (ready for RFC entries)
- `rfc-namings.md` - Terminology reference template (ready for terms)

## Verification

Check that:
- All four files exist in the specs directory
- No `{{PROJECT_NAME}}` placeholders remain
- All dates are in YYYY-MM-DD format
- Files are valid markdown

## Example

If project name is "MyProject" and specs directory is "./specs":

1. Read `assets/rfc-standard.md.template`
2. Replace `{{PROJECT_NAME}}` → `MyProject`
3. Replace `YYYY-MM-DD` → `2026-01-28` (today's date)
4. Write to `./specs/rfc-standard.md`
5. Repeat for other templates

## Notes

- If a file already exists, skip it (don't overwrite)
- Use the exact project name provided (preserve capitalization)
- Ensure directory structure exists before writing files
