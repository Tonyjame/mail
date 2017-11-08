# mail
##### http://blog.csdn.net/baidu_30000217/article/details/51550259
function sendMail($to, $title, $content) {       
        require_once '../mail/PHPMailerAutoload.php';
        $mail = new \PHPMailer(); //实例化
        $mail->IsSMTP(); // 启用SMTP
        $mail->Host='smtp.qq.com'; 
        $mail->SMTPAuth = true; 
        $mail->Username = '254****@qq.com'; //发件人邮箱
        $mail->Password ='bubjyxdzk****' ; //qq邮箱发件人独立密码
        $mail->From = '25481****@qq.com';
        $mail->FromName = '名字，随便起'; 
        $mail->AddAddress($to,"尊敬的客户");
        $mail->WordWrap = 50; 
        $mail->IsHTML(true); 
        $mail->CharSet='GBK';//这里可以是utf-8 根据业务需求自己填写
        $mail->Subject = "=?utf-8?B?" . base64_encode($title) . "?=";
        $mail->Body = $content; 
        $mail->AltBody = "这是一个纯文本的身体在非营利的HTML电子邮件客户端"; 
        $mail->Send();
}
    
$to = '*****@qq.com'; //收件人邮箱    
$title = '你好';
$content =$str;
sendMail($to, $title, $content);
