## Personal Git Flow

***

#### Tài liệu tham khảo
* [A successful Git branching model](https://nvie.com/posts/a-successful-git-branching-model/)

***

#### Chuẩn bị

* Đã tạo Repository(**Repo**) trên **Github**( Gitlab, Bitbucket,...)

* Branch mặc định của **Repo** là **master**(sẽ là nơi chứa code hoàn chỉnh nhất), branch phát triển là **develop**

* Developer có thể fork(tạo nhánh) mới từ master hoặc **develop** (thường là **develop**)

* Đã xác định được người **review**, và người có **quyền merge**

***

#### Nguyên tắc

* Mỗi 1 pull-request(**PR**, hay 1 số chỗ còn gọi là merge-request) tương ứng với một **ticket**

* Mỗi **PR** không hạn chế số lượng commit(nhưng không nên lạm dụng commit), và tùy thuộc vào yêu cầu riêng biệt của dự án, có thể có quy định về số lượng này

* Tên nhánh thường được đặt theo format ``` #[Số ticket]_[Nội dung tổng quan ticket] ``` (Ví dụ: ``` 123_login_function ```)

* **PR** phải đặt title tương ứng với title của task với format ```#[Số ticket] [Nội dung ticket]``` (Ví dụ: ``` #123 login function```)

* Commit thường được đặt theo format: ```prefix: [Nội dung]```
    * Thêm mới 1 chức năng gì đó ``` feat: [Tên chức năng thêm]```, Ví dụ: ``` feat: add login function ```

    * Sửa nội dung, hay chức năng gì đó ``` fix: [Tên chức năng sửa]```, Ví dụ  ``` fix: bug login error format data```

    * Sửa lại syntax code, formatting, white-sapce, ...:  ``` style: [Nội dung sửa đổi]```, Ví dụ: ``` style: missing white space ```

    * Cấu trúc lại code, func, ...mà không phải thêm mới chức năng ```refactor: [Nội dung cấu trúc lại]```, Ví dụ: ```refactor: change login function```

    * Thiếu test case ```test: [Nội dung]```, Ví dụ: ```test: add missing testing for login function```

    * Thay đổi tài liệu (Doccument) ```docs: [Nội dung]```, ví dụ: ```docs: add document for login function```

    * Thay đổi code để performance ```perf: [Nội dung]```, Ví dụ: ```perf: performance for login function```

* **Không** cho phép **force push** trên nhánh **không phải của mình**, **hạn chế** force push trên nhánh của chính mình, nên thảo luận với team nếu muốn **force push**

* Tại môi trường **remote và local**, tuyệt đối không được thay đổi code khi ở branch **master, hoặc develop**. Nhất định phải **tạo branch mới** để làm task

* Khi làm task mới, luôn phải đồng bộ lại branch **master và develop**, rồi mới tạo branch mới để làm task

* Nếu **PR** bị conflict, yêu cầu đồng bộ lại nhánh muốn tạo **PR** với nhánh của mình, sau đó **rebase**, fix conflict.

* Khi fix conflict cần **thảo luận với đồng đội** bị conflict code, để fix conflict tốt nhất

***

#### Quy trình

* Đồng bộ lại branch **master, develop**, và tạo branch làm việc mới
(Giả sử đang ở branch **develop**)
```git
 git pull origin develop
 git checkout -b new_branch
```

* Tiến hành làm task

* Khi đã làm xong task tiến hành commit, và push code lên branch của mình để chuẩn bị tạo **PR**
(Lưu ý có thể **commit --amend** nếu cần thiết)
```git
 git add [file_change]
 git commit -m '[message]'
 git push origin new_branch
```
* Tiến hành tạo **PR**, review qua PR của chính mình 1 lượt

* Gửi link url **PR** cho reviewer

* Tiến hành sửa lại code nếu reviewer có yêu cầu sửa code

* Khi code được review thành công, và qua quá trình test chức năng không có bug. Người có quyền **merge** sẽ merge **PR**, và khi đó ticket của bạn mới được công nhận là **xong**

***
# Contact

* [Facebook](https://www.facebook.com/mrhoangpn)
* [Twitter](https://twitter.com/Hoangphamngoc2)
* [Instagram](https://www.instagram.com/be_thelegend/)
* [Email](mailto:pnhoang.bk@gmail.com?subject=[Github])