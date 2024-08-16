[[Hub|Хаб]]
```dataviewjs
// Укажите относительный путь к папке относительно корневого каталога вашего хранилища Obsidian
const folderPath = "Daily/Days";

// Получаем все файлы из указанной папки
const files = dv.pages(`"${folderPath}"`).sort(f => f.file.name);

// Генерируем список ссылок в формате [[<name>|day_<counter>]]
files.forEach((file, index) => {
    const displayName = `day_${index + 1}`;
    dv.list([`[[${file.file.name}|${displayName}]]`]);
});
```
