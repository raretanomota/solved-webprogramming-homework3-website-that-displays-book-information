Download Link: https://assignmentchef.com/product/solved-webprogramming-homework3-website-that-displays-book-information
<br>
In this homework, you will design a website that displays book information and allows user to add books into shopping cart.

You have to design <strong>four</strong> web pages (<strong>Default.aspx</strong>, <strong>Login.aspx</strong>, <strong>BookInfo.aspx</strong>, and <strong>Cart.aspx</strong>) and a class page (<strong>Book.cs</strong>) that holds book information.

Preliminary Work

<ol>

 <li>Create a web project for the homework.</li>

 <li>Download the sample book‐cover images from the web site and put these images into a folder named <strong>images</strong> in your web folder.</li>

</ol>




<h2>Book.cs</h2>

<ol>

 <li>Add a class file named <strong>cs</strong> into your project (Add New Item, Class). This file will contain information about the books. If you encounter a message which states that this file should be in <strong>App_Code</strong> folder, then select <strong>Yes</strong> and let Visual Studio create the <strong>App_Code</strong> folder for you and put <strong>Book.cs</strong> file in this folder. After then, you will be able to use the <strong>Book</strong> class in</li>

</ol>

your application like any other classes of .NET library.

<ol start="2">

 <li>Add member variables to the class <strong>Book</strong> which are <strong>BookID</strong> (integer), <strong>Title</strong> (string), <strong>Author</strong> (string), <strong>Publisher</strong> (string), <strong>PageNumber</strong> (int), and <strong>ImageUrl</strong> (string).</li>

 <li>Define a constructor for the <strong>Book</strong> class which takes all of its member variables as parameter</li>

</ol>

(<strong>Hint</strong>: In Visual Studio, type <strong>ctor</strong> and press <strong>TAB</strong> key. This constructs an empty constructor  for the class. After then, change the constructor parameters and implementation). 4. Finally, your Book class should be like this:




public class Book

{ public int BookID; public string Title; public string Author; public string Publisher; public int PageNumber; public string ImageUrl;




public Book(int BookID, string Title, string Author, string Publisher, int PageNumber, string ImageUrl)

{ this.BookID = BookID; this.Title = Title; this.Author = Author; this.Publisher = Publisher; this.PageNumber = PageNumber; this.ImageUrl = ImageUrl;

}

}

<h2>Design of Default.aspx</h2>

When loaded, <strong>Default.aspx</strong> page should check whether the user is logged in or not. This check should be accomplished by a <strong>cookie</strong> check. The cookie should contain only the <strong>first name</strong> and <strong>last name</strong> of




1

the user. If no such cookie is defined, then <strong>Default.aspx</strong> should display a <strong>message</strong> and a <strong>link</strong> to the <strong>Login.aspx </strong>as in Fig. 1.










<strong>Fig. 1 </strong>   <strong>– Default.aspx when user is not logged in. </strong>




<strong>Fig. 2 – Login.aspx page </strong>




<h2>Desig<sub>   </sub>n of Login.aspx</h2>

<strong>Login.aspx </strong>is very simple web page; it contains only<strong> two textboxes </strong>for<strong> first name </strong>and<strong> last name</strong>, and a <strong>Login</strong> button as in Fig. 2. There will be no password check. Any user that completes this form will be considered as a logged in user.

When the <strong>Login</strong> button is clicked , <strong>first name</strong> and <strong>last name</strong> will be written into a cookie named <strong>UserInfo </strong>for<strong> one month </strong>and the page will be redirected to<strong> Default.aspx </strong>and<strong> Default.aspx </strong>will display<strong> user info </strong>on the left and a<strong> list of books </strong>on the right as in Fig. 3. The information about the  books is as the following:




<table width="624">

 <tbody>

  <tr>

   <td width="54"><strong>Book </strong><strong>ID </strong></td>

   <td width="236"><strong>Title </strong> </td>

   <td width="186"><strong>Author </strong> </td>

   <td width="72"><strong>Publisher </strong> </td>

   <td width="76"><strong>Page Number </strong></td>

  </tr>

  <tr>

   <td width="54">1</td>

   <td width="236">ASP.NET 3.5 Unleashed</td>

   <td width="186">Stephen Walther</td>

   <td width="72">Sams</td>

   <td width="76">1920</td>

  </tr>

  <tr>

   <td width="54">2</td>

   <td width="236">ASP.NET Ev olution</td>

   <td width="186">Dan Kent</td>

   <td width="72">Sams</td>

   <td width="76">384</td>

  </tr>

  <tr>

   <td width="54">3</td>

   <td width="236">Mastering Web Develop ment with Microsoft Visual Studio 2005</td>

   <td width="186">John Pa ul Mueller </td>

   <td width="72">Sams </td>

   <td width="76">848 </td>

  </tr>

  <tr>

   <td width="54">4  </td>

   <td width="236">Beginning A SP.NET 2.0  </td>

   <td width="186">Chris Hart, John Kau fman,Dave Su ssman, and ChrisUllman</td>

   <td width="72">Wrox  </td>

   <td width="76">792  </td>

  </tr>

  <tr>

   <td width="54">5  </td>

   <td width="236">Beginning A SP.NET 3.5 in C# 2008:From Novice to Professional, Secon d Edition</td>

   <td width="186">Matthe w MacDonal d  </td>

   <td width="72">Apress  </td>

   <td width="76">954  </td>

  </tr>

 </tbody>

</table>

<strong>Table 1 – Book info </strong>




<strong>Fig. 3 – De fault.aspx page after user is logged in </strong>




<strong>Default.aspx </strong>should display a link to<strong> Cart.aspx </strong>and a<strong> Logout </strong>button on the left. When the<strong> Logout </strong>button is clicked, the <strong>UserInfo</strong> cookie should be remove d and Fig. 1 should be di splayed.




<strong>Default.aspx </strong>should display the titles of the books on the right with a<strong> link </strong>on each one. Each link should navigate to <strong>BookInfo.aspx</strong> with query string named <strong>id</strong> (e.g. <strong>BookInfo.aspx?id=5</strong>).




When <strong>Default.aspx</strong> page is first loaded, it should create five <strong>Book</strong> objects and put all them in to the <strong>Session state</strong>.







3

<h2>Desig<sub>   </sub>n of BookInfo.aspx</h2>

When a book title is clicked in <strong>D efault.aspx</strong>, the information about the book should be displayed in <strong>BookInfo.aspx </strong>page as in Fig. 4. Book ID should be taken from<strong> query string </strong>with name<strong> id</strong>.










<strong>Fig. 4 – Bo okInfo.aspx p age with a vali d book id </strong>




If <strong>BookInfo.aspx</strong> is requested without any query string or the book ID does not exist, then it should display an appropriate message as in Figures 5 and 6.










<strong>Fig. 5 – BookInfo.aspx when no query string is provided </strong>










<strong>Fig. 6 – BookInfo.aspx when an invalid ID is provided </strong>




If a valid book ID is p resented, then <strong>BookInfo.aspx</strong> page should bring the desired book info from the <strong>Session </strong>state and di splay the book info with its cover image.




There also should be an <strong>Add to Cart</strong> button, a link to <strong>Cart.aspx</strong> and a link to <strong>Default.aspx</strong> as in Fig. 4.




When <strong>Add to Cart</strong> button is clicked, the book ID should be added in an <strong>ArrayList</strong> object in <strong>Session</strong> state that holds the selected book IDs. After the book is added into this <strong>ArrayList</strong> object, the user should be informed about this as in Fig. 7.




If that book is already in the cart, an appropriate message should be displayed as in Fig. 8.




<strong>BookInf</strong> <strong>o.aspx </strong>should also present links to<strong> Cart.aspx </strong>and<strong> Default.aspx</strong>.




<strong>Fig. 7 – Bo okInfo.aspx after Add to Cart button is clicked and the book is successfully added to the cart </strong>

<strong>Fig. 8 – Bo okInfo.aspx page when Add to Cart button is clicked but the book was already in the cart. </strong>




<h2>Basic Informati on About <em>ArrayLis t</em> Class</h2>

<strong>ArrayList </strong><sub>             </sub>class can be used to st ore items in an array in object‐oriented manner. You can store book IDs in an <strong>ArrayList</strong> object. An <strong>ArrayList</strong> objec t is created by the new operator:




ArrayList SelectedBookIndices = new ArrayList();




An item can be adde d to the <strong>ArrayList</strong> by <strong>Add()</strong> method:




SelectedBookIndices.Add(id);




Here, <strong>id</strong> can be of an y class. For the demonstration, we assume that <strong>id</strong> is of type <strong>string</strong>.




In order to check whether an item exists in the <strong>ArrayList</strong> or not, <strong>Contains()</strong> method can be used:




if  (SelectedBookIndices.Contains(id))

{

…

}




To remove an item, <strong>Remove()</strong> method can be used. If you want to remove all items, you can use <strong>Clear() </strong>method.




<h2>Design  of Cart.aspx</h2>

<strong>Cart.aspx </strong>should display all book s that are added to the shopping cart as in Fig. 9 . The IDs of the selected books should be taken from <strong>Session</strong> state as described above and information about the books should also be taken from the <strong>Session</strong> state which is put into the <strong>Session</strong> state by <strong>Def ault.aspx</strong> when it is first displayed. If there is no book in the shopping cart, a message should be displayed as in Fig. 10.




<strong>Cart.aspx </strong>page should also presents a link to the main page.




<strong>Fig. 9 </strong>  <strong>– Cart.aspx when there are books in the shopping cart </strong>


