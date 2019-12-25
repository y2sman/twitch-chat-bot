# Twitch Chat Bot

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

[Command Table](https://www.notion.so/04b2c750e7f14f6895d1c717f8ccbde1)

관리용 명령어의 경우, Streamer와 Moderator 이외의 경우 사용할 수 없습니다.

### 주의사항

명령어 이름은 띄어쓰기를 지원하지 않습니다! 띄어쓰기가 필요한 명령어의 경우 '_'와 같이 대체해주세요.
