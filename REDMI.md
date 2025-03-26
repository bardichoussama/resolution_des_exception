# Handling Unique Constraint Violation in Laravel

## Problem:
When using the following migration for the `articles` table:

```php
public function up(): void
{
    Schema::create('articles', function (Blueprint $table) {
        $table->id();
        $table->string('title')->unique(); // 'title' column has a unique constraint
        $table->timestamps();
    });
}

Solution:
Steps to Fix the Issue:
1. Update Your Migration File
Modify your articles table migration to include the content column.


Modifier
public function up(): void
{
    Schema::create('articles', function (Blueprint $table) {
        $table->id();
        $table->string('title')->unique(); // Add a unique constraint for title
        $table->text('content'); // Add the content column
        $table->timestamps();
    });
}