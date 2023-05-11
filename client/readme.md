# Web Client

Web Client adalah aplikasi yang berjalan di browser. Web Cient biasanya menggunakan HTML untuk user interface, CSS untuk user interface styling, JS untuk membuat logika untuk interactivity.

## Javascript

Javascript adalah bahasa yang digunakan untuk menambahkan interactivity ke html melalui Document Object Model. Javascript juga dapat menggunakan fitur yang disediakan oleh browser melalui Web API.

Typescript adalah superset dari javascript. Typescript menambah *type system* di javascript. Typescript tidak dapat dijalankan dimanapun, melainkan kode typescript dicompile kembali ke javascript.

Beberapa framework untuk membuat web client di javascript:

- [React](./react.md)

	React merupakan *Gold Standard Library* untuk membuat web client, artinya telah banyak dikenal dan digunakan para developer. React menggunakan [JSX](./react.md#jsx) untuk membuat ui di javascript ketimbang html. Hal ini memudahkan untuk memasukan data ke ui. React menggunakan **babel** untuk mengubah JSX menjadi vanilla javascript, karena browser tidak mengerti JSX, melainkan membuat Virtual DOM untuk menjalankan javascript yang di-*build* oleh react. React juga menyediakan [Hooks](./react.md#hooks) untuk mengelola state (**State Management**) dalam component.
	
	React tidak menyediakan banyak fitur, melainkan bergantung pada komunitas untuk membuat library:
	
	- React Router
	- Mantine
	- Material UI
	- Chakra UI
	- Redux
	
- [Svelte](./svelte.md)
	
	Svelte menggabungkan script, html, dan css dalam satu file sebagai component, lalu component tersebut digabungkan dengan component lainya untuk membuat web client app. Svelte memiliki syntax sendiri untuk mengintegrasikan data ke html. Svelte juga menyediakan **Store** untuk *State Management*. Svelte bekerja sebagai compiler menjadi vanilla javascript yang dimengerti oleh browser. Keuntunganya adalah performa yang lebih cepat karena svelte tidak membuat virtual dom seperti react setelah fase build.
	
- JQuery
	
	Jquery adalah library untuk berinteraksi dengan web api seperti DOM dan Ajax. Jquery sangat mudah untuk di-integrasikan ke dalam project karena jquery di-*build* menjadi satu script yang dapat di-import dari cdn melalui link. Jquery sudah jarang digunakan karena beberapa fiturnya telah ditambahkan ke browser segbagai buit-in web api sperti, `querySelector` dan `fetch` api.

## CSS

Css digunakan untuk mengubah default style yang diberikan html. Tapi, css kekurangan fitur programatic seperti kondisi, loop, dsb. Maka dari itu dibuat banyak library css untuk menambahkan fitur diatas css:

- Talwindcss, menyediakan properti dasar dari css dalam bentuk html class.
- Bootstrap, menyediakan component siap pakai seperti button, form, table, grid, dll.
- Sass, menambah fitur programatic seperti kondisi, loop, array, dll.
- Postcss, menambah boilerplate seperti `--moz-` untuk compatibility