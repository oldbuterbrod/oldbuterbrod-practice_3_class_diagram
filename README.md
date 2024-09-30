# Диаграмма классов библиотеки
Сидоров Максим Максимович ЭФМО-02-24
![image](https://github.com/user-attachments/assets/792fec30-33e6-44cd-847b-fe43be90f531)




## Классы и их описание

1. User (Пользователь):
   Атрибуты:
   userid: int — уникальный идентификатор пользователя.
   name: string — имя пользователя.
   email: string — электронная почта.
   phoneNum: string — номер телефона.
   
   Методы:
   login() — вход в систему.
   logout() — выход из системы.
   
   Наследуется классами Reader и Librarian.

2. Librarian (Библиотекарь):
   Методы:
   addBook(Book) — добавление книги.
   updateBook(Book) — обновление информации о книге.
   removeBook(Book) — удаление книги.

3. Reader (Читатель):
   Атрибуты:
   penalties: List<Penalty> — список штрафов, связанных с читателем.
   
   Методы:
   rentBook(Book, Date, int) — аренда книги.
   returnBook(Book) — возврат книги.
   viewRentedBooks() — просмотр арендованных книг.

5. Book (Книга):
   Атрибуты:
   bookid: int — уникальный идентификатор книги.
   title: String — название книги.
   author: String — автор.
   genre: String — жанр.
   publicationDate: Date — дата публикации.
   isbn: String — международный стандартный номер книги.
   numPages: String — количество страниц.
   stock: int — количество доступных экземпляров.
   
   Методы:
   getBookInfo() — получение информации о книге.

7. Rental (Аренда):
   Атрибуты:
   loanID: int — уникальный идентификатор аренды.
   book: Book — ссылка на арендованную книгу.
   reader: Reader — ссылка на читателя.
   startDate: Date — дата начала аренды.
   dueDate: Date — срок возврата.
   isReturned: boolean — статус возврата.

   Методы:
   calculateOverdue(): int — расчет просрочки.
   returnBook() — возврат книги.

9. Penalty (Штраф):
   Атрибуты:
   penaltyID: int — уникальный идентификатор штрафа.
   amount: double — сумма штрафа.
   issueDate: Date — дата наложения штрафа.
   isPaid: boolean — статус оплаты штрафа.

   Методы:
   payPenalty() — оплата штрафа.
   calculatePenalty(Loan) — расчет суммы штрафа на основе аренды.

## Взаимосвязи между классами

Наследование: Классы Librarian и Reader наследуют от класса User, позволяя им использовать общие атрибуты и методы.

Ассоциации:
Класс Reader имеет ассоциацию с классом Penalty, что означает, что один читатель может иметь множество штрафов.
Класс Rental имеет ассоциации с классами Book и Reader, что позволяет отслеживать, какая книга арендована каким читателем.

