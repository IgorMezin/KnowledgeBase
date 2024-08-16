[[Education|Образование]]
**2024**
```dataviewjs
// Укажите относительный путь к папке относительно корневого каталога вашего хранилища Obsidian
const folderPath = "Education/Книги/2024";

// Получаем все файлы из указанной папки
const files = dv.pages(`"${folderPath}"`).sort(f => f.file.name);

// Генерируем список ссылок в формате [[<name>|day_<counter>]]
files.forEach((file, index) => {
    dv.list([`[[${file.file.name}|${file.file.name}]]`]);
});
```
