def insert_readme_code(original_readme_path, code_file_path, output_readme_path):
    # 프로젝트 README.md 파일 읽기
    with open(original_readme_path, 'r', encoding='utf-8') as readme_file:
        readme_content = readme_file.read()

    # 코드 파일 읽기
    with open(code_file_path, 'r', encoding='utf-8') as code_file:
        code_content = code_file.read()

    # README.md에 코드 블록 삽입
    updated_readme = readme_content.replace("```python\n```", f"```python\n{code_content}\n```")

    # 수정된 내용을 새로운 README.md 파일에 저장
    with open(output_readme_path, 'w', encoding='utf-8') as output_readme_file:
        output_readme_file.write(updated_readme)

# 프로젝트 정보에 맞게 파일 경로 및 이름을 수정하세요.
original_readme_path = "README.md"  # 기존의 README.md 파일 경로
code_file_path = "proj/README.md"   # 삽입할 코드가 있는 파일 경로
output_readme_path = "UPDATED_README.md"  # 새로운 README.md 파일의 경로 및 이름

insert_readme_code(original_readme_path, code_file_path, output_readme_path)

