---
title: 'Khám phá AI Agent từ A-Z'
date: 2025-02-28
permalink: /posts/2025/02/blog-post-1/
tags:
  - LLM
  - AI Agent
  - AI
---

## 1. AI Agent là gì?
### 1.1. Định nghĩa AI Agent 

Tác nhân AI (AI Agent) là một hệ thống trí tuệ nhân tạo có khả năng nhận thức môi trường xung quanh, nhận thông tin phản hồi và đưa ra hành động phù hợp dựa trên những thông tin đó. Trong một số tài liệu, tác nhân AI còn được định nghĩa là một hệ thống có thể giải quyết các vấn đề phức tạp, lập kế hoạch hành động và thực hiện các kế hoạch này nhờ vào bộ công cụ được trang bị. Nói cách khác, một tác nhân AI được xác định bởi môi trường mà nó tương tác và các hành động mà nó có thể thực hiện trong môi trường đó.

Môi trường hoạt động của một tác nhân AI (agent) được xác định dựa trên ứng dụng cụ thể. Ví dụ, nếu agent được thiết kế để chơi game (VD: Minecraft, Go hoặc Dota), thì trò chơi chính là môi trường của agent. Trong trường hợp agent được sử dụng để tìm kiếm thông tin trong cơ sở tri thức, môi trường của agent là cơ sở tri thức bao gồm các tài liệu nội bộ hoặc cơ sở dữ liệu.

Agent thực hiện hành động thông qua các công cụ (tools). Ví dụ, một agent có thể sử dụng công cụ tìm kiếm thông tin để lấy dữ liệu mong muốn, như lịch sử mua sắm của khách hàng, nhằm đưa ra các khuyến nghị phù hợp. AI Agent có thể thực hiện các lời gọi API để tự động gửi email phản hồi hoặc thực hiện các giao dịch tài chính thay cho bạn. Rất nhiều các ứng dụng AI mà chúng ta đang sử dụng chính là các agent với khả năng truy cập vào các công cụ. ChatGPT là một agent với khả năng tìm kiếm thông tin trên Web, thực thi mã Python, sinh ảnh. Các hệ thống RAG là các agents sử dụng các công cụ tìm kiếm văn bản, tìm kiếm hình ảnh và công cụ thực hiện các truy vấn SQL. 


### 1.2. Thành phần cơ bản của AI Agent 

Một hệ thống AI Agent hoạt động dựa trên mô hình ngôn ngữ lớn (LLM) bao gồm những thành phần cơ bản như trong hình dưới đây: 

 Thành phần cơ bản của AI Agent sẽ gồm 3 phần: Mô hình, Công cụ và Tầng điều phối. Cụ thể như sau:

Mô hình (Model) 

Mô hình là thành phần quan trọng của AI Agent, đóng vai trò trung tâm trong việc giúp Agent lập kế hoạch, dự đoán và lựa chọn các hành động phù hợp nhất để đạt được mục tiêu một cách hiệu quả. Mô hình sử dụng trong Agent là mô hình ngôn ngữ lớn (LLMs) hoặc các các mô hình đa thể thức, có thể xử lý nhiều loại dữ liệu khác nhau

Để hoạt động hiệu quả, mô hình cần có khả năng hiểu các chỉ thị từ con người (instruction following), khả năng suy luận, lập kế hoạch hành động, và lựa chọn công cụ phù hợp. Trong một số trường hợp, để cải thiện hiệu quả, cần tinh chỉnh (fine-tuning) mô hình bằng cách sử dụng dữ liệu chứa các ví dụ thực tế về: Các ngữ cảnh ứng dụng của Agent, Cách lập luận mà chúng ta mong muốn Agent làm, và những công cụ mà Agent sử dụng trong các trường hợp đó. Điều này giúp mô hình đáp ứng tốt hơn với các yêu cầu thực tiễn của Agent.

Công cụ (Tools) 

Mặc dù các mô hình AI tạo sinh có khả năng ấn tượng trong việc thực hiện các nhiệm vụ như tạo hình ảnh hoặc văn bản, chúng vẫn bị giới hạn trong khả năng tương tác với thế giới bên ngoài. Công cụ đóng vai trò mở rộng năng lực của AI Agent, trang bị cho Agent khả năng tương tác với dữ liệu và các dịch vụ bên ngoài mà mô hình đứng một mình không thể thực hiện được

Công cụ hỗ trợ Agent trong việc:

    Thu thập dữ liệu và thông tin từ thế giới thực,
    Nhận biết môi trường xung quanh,
    Thực hiện các hành động cụ thể.

Ví dụ, một công cụ có thể dùng để cập nhật thông tin khách hàng trong cơ sở dữ liệu, trong khi công cụ khác có thể truy xuất lịch sử giao dịch của khách hàng.

Tầng điều phối (Orchestration layer) 

Tầng điều phối giữ vai trò quản trị cách thức Agent nhận thông tin, suy luận, lên kế hoạch hành động, xác định hành động hoặc quyết định tiếp theo dựa trên suy luận. Độ phức tạp của tầng điều phối phụ thuộc lớn vào Agent và những tác vụ mà nó thực hiện. Chi tiết về cách thức Agent lên kế hoạch, suy luận và điều phối các quyết định, hành động sẽ được mô tả kỹ hơn trong các phần sau.
## 2. AI Agent hoạt động như thế nào?

Tác nhân AI hoạt động theo một vòng lặp liên tục bao gồm các bước: (1) Thu thập thông tin; (2) lập kế hoạch; (3) đánh giá kế hoạch và điều chỉnh; (4) thực thi hành động bằng cách sử dụng các công cụ; (5) đánh giá kết quả của hành động và đưa ra điều chỉnh về kế hoạch nếu cần. 

Để dễ hình dùng hơn, hãy tưởng tượng bạn là một đầu bếp đang chuẩn bị bữa tiệc cho khách hàng. Để thực hiện công việc này, bạn có thể cần thực hiện các bước sau: 

    Thu thập thông tin, như yêu cầu về món ăn của khách hàng, sở thích của khách hàng, những nguyên liệu đang có trong bếp 

    Dựa trên các thông tin đã thu thập được, suy nghĩ và lập kế hoạch về các món ăn mà bạn sẽ làm 

    Bạn thực hiện các hành động để làm các món ăn như: thái rau, trộn gia vị, nướng thịt 

Ở mỗi giai đoạn trong quy trình, bạn cần thực hiện các điều chỉnh khi cần thiết, tinh chỉnh kế hoạch của mình, chẳng hạn khi nguyên liệu được sử dụng hết hoặc khi nhận được phản hồi từ khách hàng, và sử dụng các kết quả trước đó để xác định bước hành động tiếp theo.


 

Như vậy trong AI Agent hoạt động tốt hay không phụ thuộc vào khả năng lập, điều chỉnh kế hoạch hành động khi nhận thông tin và những công cụ mà Agent có thể sử dụng. Trung tâm của năng lực nhận thức của Agent nằm ở tầng điều phối – thành phần chịu trách nhiệm duy trì bộ nhớ, trạng thái, suy luận và lập kế hoạch. 
### 2.1. Lập kế hoạch 

Planning là một quy trình cốt lõi trong hoạt động của AI agent, nơi hệ thống tạo ra một lộ trình để đạt được mục tiêu của nhiệm vụ. Để hoàn thành một nhiệm vụ, AI agent phải trải qua các bước: hiểu nhiệm vụ, tạo kế hoạch, xác minh kế hoạch, thực thi, và điều chỉnh dựa trên phản hồi. Quy trình này giúp tối ưu hóa hiệu quả, giảm sai sót không cần thiết và tăng khả năng hoàn thành nhiệm vụ thành công.

Mô hình ngôn ngữ lớn thường được sử dụng trong bước lập kế hoạch. Các kỹ thuật prompt engineering và lập luận (reasoning) hiện đại được áp dụng để cải thiện hiệu quả của quy trình lập kế hoạch. Các framework cho prompt engineering và kỹ thuật lập luận phổ biến được sử dụng bao gồm: 

    ReAct (Reasoning and Acting) là một framework kết hợp giữa suy luận (Reasoning) và hành động (Acting) trong quá trình mô hình AI xử lý yêu cầu từ người dùng, được đề xuất bởi tác giả Yao vào năm 2022. Framework lập luận này kết hợp suy nghĩ và hành động, phân tích kết quả đầu ra, giúp AI vừa lập kế hoạch vừa thực thi và điều chỉnh ngay lập tức. 

    Chain-of-Thought (CoT): đây là kỹ thuật prompt engineering để hướng dẫn phép mô hình suy luận qua từng bước trung gian, phù hợp với các nhiệm vụ phức tạp. 

    Tree-of-Thoughts (ToT): Khám phá nhiều phương án song song để lựa chọn giải pháp tối ưu. 

AI Agent có thể áp dụng một hoặc nhiều kỹ thuật trên,  hoặc nhiều kỹ thuật khác, để chọn hành động tốt nhất tiếp theo cho yêu cầu của người dùng. 
Ví dụ về khả năng lập kế hoạch trong công cụ Deep Research của Gemini Advanced

### 2.2. Công cụ 

Việc sử dụng công cụ là cách mà các tác nhân AI (AI Agents) mở rộng khả năng của các mô hình ngôn ngữ lớn (LLMs), vốn bị giới hạn bởi dữ liệu mà chúng đã được huấn luyện. Công cụ giúp các Agent tương tác với dữ liệu và các dịch vụ bên ngoài. Chúng ta có thể phân loại công cụ thành hai nhóm chính:

    Lời gọi hàm (Function calling) 

    Bổ sung tri thức từ kho dữ liệu (Data Store) 

### Function calling 

Trong kỹ thuật phần mềm, hàm (function) là các module mã độc lập được thiết kế để thực hiện một nhiệm vụ cụ thể và có khả năng tái sử dụng. Nhà phát triển chịu trách nhiệm viết các hàm, xác định logic khi nào nên gọi hàm nào, và đảm bảo rằng đầu vào (input) và đầu ra (output) của hàm đáp ứng đúng yêu cầu. Trong thế giới AI Agents, Function Calling hoạt động tương tự, nhưng điểm khác biệt là mô hình ngôn ngữ lớn (LLM) sẽ tự động quyết định thời điểm sử dụng hàm và cung cấp các tham số cần thiết dựa trên thông số kỹ thuật của hàm đó.

Trong Function Calling, việc xử lý logic và gọi API không thực hiện trực tiếp trong agent mà được chuyển sang phía client-side (ứng dụng khách). Cách làm này giúp nhà phát triển kiểm soát chi tiết hơn cách dữ liệu được xử lý và di chuyển trong ứng dụng. Ví dụ, khi agent cần lấy thông tin từ Google Flights API, thay vì tự gọi API, agent sẽ đưa ra một hàm (Function) với tên và các tham số phù hợp. Sau đó, ứng dụng client sẽ chịu trách nhiệm gọi API, nhận kết quả và thực hiện các bước xử lý bổ sung trước khi gửi dữ liệu trở lại cho a

---
* [1. Tham Khảo](https://www.linkedin.com/pulse/ai-agent-l%C3%A0-g%C3%AC-kh%C3%A1m-ph%C3%A1-t%C3%A1c-nh%C3%A2n-t%E1%BB%AB-a-z-pham-quang-nhat-minh-m59sc/?trackingId=hUsD6YnX5Abb%2FZ5p6GdZVw%3D%3D)