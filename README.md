# Twitch Chat Bot

## 참고
[추가적인 설명이 있는 블로그](https://y2sman.github.io/2019/12/25/2019_12_25/)

## 설치

python3 에서 작동합니다.

    pip3 install requests
    pip3 install irc

위의 두 패키지가 필요합니다.

## How to Use

    def main():
        username  = "Bot 닉네임 입력"
        client_id = "Client-ID"
        token     = "oauth"
        channel = "방송 닉네임 입력"
        delay_time = 20
    
        bot = TwitchBot(username, client_id, token, channel, delay_time)
        bot.start()

사용하기에 앞서, delay_time을 적절하게 조정해주세요. default값은 20초입니다. 따로 사용하는 싹둑이나 나이트봇이 있다면, 해당 봇의 !command나 !명령어 명령어의 재사용 시간과 똑같이 설정하는걸 권장합니다.

### 자동 명령어 백업

명령어를 수정할때마다 자동으로 백업을 합니다. 확장자 없는 command 파일과 command_time 파일은 이를 위한 파일입니다. 삭제할 경우, 복원 기능이 작동하지 않습니다.

단, 복원 기능은 자동이 아닙니다. 혹시라도 봇을 껏을때 명령어 복원을 원한다면, '!복원'을 입력해주세요.

### Command Table
|명령어|내용|사용법|
|:---|:---|:---|
|!백업|현재 명령어 수동 백업 (멤버 포함)|!백업|
|!복원|저장된 명령어 복원|!복원|
|!멤버|저장된 멤버가 있다면, 멤버를 보여줍니다. 없다면 기본 문구를 출력합니다.|!멤버|
|!멤버삭제|멤버에 저장된 데이터를 전체 삭제합니다.|!멤버삭제|
|!멤버추가 {Member_data}|{Member_data}에 입력한 데이터가 !멤버에서 보여집니다.|!멤버추가 테스트 <br> !멤버추가 테스트1, 테스트2, 테스트3|
|!명령어|현재 저장된 명령어 리스트를 보여줍니다.|!명령어|
|!명령어 추가 {Command_name} {Command_data}|{Command_data}에 입력한 데이터가 {Command_name}을 입력하면 출력됩니다.|!명령어 추가 크리스마스 크리스마스는 12월 25일이다.|
|!명령어 삭제 {Command_name}|{Command_name}의 명령어를 삭제합니다.|!명령어 삭제 크리스마스|

관리용 명령어의 경우, Streamer와 Moderator 이외의 경우 사용할 수 없습니다.

### 주의사항

명령어 이름은 띄어쓰기를 지원하지 않습니다! 띄어쓰기가 필요한 명령어의 경우 '_'와 같이 대체해주세요.
