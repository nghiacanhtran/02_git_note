# git_note

## Git common

- commit & push an empty Git folder or directory:  thêm file .gitkeep tới folder
- clone repo: `git clone 'link_repo'`
- switch-branch: `git checkout <existing_branch>`
- create new branch: `git checkout -b <new_branch>`
- show current branch : `git branch`
- push code : `git push -uf origin main`
- discard local file: `git restore pathFile`

## Git Log

- Command
  - `git log` : Hiển thị danh sách commit cùng với messages, thời gian tạo commit, người tạo commit, các commit được sắp xếp theo thứ tự từ mới đến cũ.
  - `git log --reverse`: Hiển thị tương tự git log, nhưng thứ tự sắp xếp commit ngược lại
  - `git log -p`: Hiển thị chi tiết thông tin commit, bao gồm cả nội dung thay đổi (thêm/xóa dòng code nào), tuy nhiên nếu có nhiều sự thay đổi, cách này nhìn khá là dài và rườm rà
  - `git log -p <filename>`: Thêm vào tên file cụ thể sẽ trả về những commit thay đổi file đó, ví dụ git log -p app/models/user.rb sẽ trả về danh sách các commit có sự thay đổi file user.rb cùng với sự nội dung thay đổi, nếu bạn không quan tâm đến nội dung thay đổi, có thể bỏ -p, hoặc thay bằng --oneline để xem ngắn gọn hơn. Trong một vài trường hợp có thể nhầm lẫn giữa tên file và tên branch, nên thêm -- để tránh nhầm lẫn, ví dụ git log -p -- app/models/user.rb
  - `git log -p -S <query>`: -S viết tắt của search, ví dụ như khi viết git log -p -S password, sẽ trả về danh sách các commit mà trong các thay đổi về code có từ "password", tương tự có thể bỏ -p hay thêm --oneline, nhưng mình thường viết như vậy. Nếu như bạn muốn sử dụng regular expression thay vì một chuỗi, bạn có thể thay bằng -G `<regex>`
  - `git log -p --grep <query>`: tương tự như -S, --grep tìm kiếm những commit có messages có chứa từ trong `<query>`, nếu cụm từ tìm kiếm có dấu cách thì phải để trong ngoặc kép, ví dụ git log -p --grep "change password"
  - 1git log --stat1: hiển thị commit cùng số lượng thêm và xóa bao nhiêu dòng trong mõi file trong commit đó, cách này khá hữu ích khi muốn xem sự thay đổi trong mỗi commit một cách ngắn gọn.

- Action
  - `<spacebar>`: nhảy tới trang tiếp theo
  - `/<term>`, ?<term>: tìm kiểm trong trang xem kết quả, ví dụ /password sẽ nhảy đến dòng có chứa từ khóa password và highlight kết quả
  - `n`: dùng cùng với / hoặc ?, để nhảy đến kết quả tìm kiếm tiếp theo
  - `N`: giống như n nhưng nhảy đến kết quả tìm kiếp trước đó
  - `b`: quay về trang trước
  - `q`: thoát khỏi trang kết quả Một mẹo khá hay khi xem commit là gõ /^commit, câu lệnh sẽ highlight tất cả từ commit, sau đó chỉ việc gõ n hoặc N để chuyển đến commit tiếp theo hoặc trước đó
