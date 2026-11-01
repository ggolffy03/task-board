# 📋 PM Board — Personal Project Management

แอปจัดการงานส่วนตัวแบบไม่มี backend — ข้อมูลทั้งหมดอยู่ใน `data.json` อัปเดตผ่าน Discord (Hermes)

## Live

https://ggolffy03.github.io/task-board/

## ฟีเจอร์

- **หลายโปรเจกต์** — แต่ละโปรเจกต์มีบอร์ดของตัวเอง (แถบซ้ายสลับโปรเจกต์ได้)
- **3 มุมมอง** — Dashboard (ภาพรวม+สถิติ) / Kanban (บอร์ด 4 คอลัมน์) / List (ตาราง)
- **ลำดับความสำคัญ** — สูง / กลาง / ต่ำ
- **กำหนดวัน** — เตือน "เลยกำหนด" / "วันนี้" / "ใกล้ถึง" อัตโนมัติ
- **แท็ก / งานย่อย (subtask) / คำอธิบาย / % ความคืบหน้า**
- Dark theme (GitHub style)

## วิธีใช้

สั่งงานผ่าน Discord แล้วผม (Hermes) แก้ `data.json` → commit + push → หน้าอัปเดตเอง (~30 วิ)

## โครงสร้าง data.json

```json
{
  "updated": "YYYY-MM-DD",
  "projects": [
    {
      "id": "p-001",
      "name": "ชื่อโปรเจกต์",
      "description": "...",
      "color": "#58a6ff",
      "columns": ["วางแผน", "กำลังทำ", "รอทดสอบ", "เสร็จ"],
      "tasks": [
        {
          "id": "t-001",
          "title": "ชื่องาน",
          "column": "กำลังทำ",
          "description": "",
          "progress": 0,
          "priority": "กลาง",
          "due": "YYYY-MM-DD",
          "tags": ["..."],
          "subtasks": [{ "title": "...", "done": false }],
          "updated": "YYYY-MM-DD"
        }
      ]
    }
  ]
}
```

- `column` ต้องตรงกับใน `columns` เป๊ะ
- `progress` = 0-100, `priority` = สูง/กลาง/ต่ำ, `due` = null หรือ YYYY-MM-DD
