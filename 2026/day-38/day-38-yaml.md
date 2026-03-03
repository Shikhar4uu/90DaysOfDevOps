## What are the two ways to write a list in YAML?
1. Block Style --
tools:
  - docker
  - git
  - linux

2. Inline Style --
hobbies: [reading, gaming, fitness]


## When would you use | vs >?
 | (Literal Block) --
- Preserves line breaks
- Use for:
    - shell scripts
    - config files
    - certificates
    - multi-line logs

 > (Folded Block) --
- Converts newlines into spaces or all lines become one single line. 
- Use for:
    - Long description
    - Paragraph text
    - documentation strings



## Spot the Difference
Read both blocks and write what's wrong with the second one:
# Block 1 - correct
name: devops
tools:
  - docker
  - kubernetes
# Block 2 - broken
name: devops
tools:
- docker
  - kubernetes
# Ans: - docker is not indented under tools. list items must align properly under the parent key.


## What I Learned -
1. YAML uses spaces only — tabs break everything.
2. Indentation is importatnt even 1 space mistake causes errors.
3. Lists can be written in block style (- item) or inline style [item1, item2].


## YAML Aha Moment -
my biggest learning was that a single TAB can break the entire file.
YAML is extremely strict about indentation.


## YAML Debugging Summary (Day 38) or error faced while running yaml files

### 1. CRLF vs LF (Line Endings)
- Problem: "wrong new line character: expected \n"
- Cause: File had Windows line endings (CRLF).
- Solution: Run `dos2unix filename.yml` or change CRLF → LF in VS Code.

### 2. Missing `---`
- Problem: Warning about missing document start.
- Meaning: `---` marks start of YAML document.
- Solution: Add `---` at top (optional but recommended).

### 3. Extra Blank Lines
- Problem: "too many blank lines"
- Cause: Empty line at top or bottom of file.
- Solution: Remove extra blank lines.

### 4. Line Too Long
- Problem: Line exceeded 80 characters.
- Solution: Break long sentence into multiple lines.

### 5. Tabs vs Spaces
- Problem: YAML does not allow real TAB characters.
- Solution: Use spaces only (check VS Code shows "Spaces: 2").

### 6. Multi-line Strings
- `|` → Keeps line breaks (for scripts).
- `>` → Converts newlines into spaces (for paragraphs).

---

### Key Learning - 
YAML is very strict about formatting. 
Small mistakes like tabs, wrong indentation, or Windows line endings can break everything.



