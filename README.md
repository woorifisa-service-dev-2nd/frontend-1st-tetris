<div align= "center">
    <img src="https://capsule-render.vercel.app/api?type=soft&color=0:df90ee,100:3c9ab9&height=120&text=Most%20Challenging%20Tetris&animation=twinkling&fontColor=ffffff&fontSize=70" />
    </div>
    <div style="text-align: left;"> 
    <h2 style="border-bottom: 1px solid #d8dee4; color: #282d33;"> 💻 프로젝트 및 팀원소개 </h2>
		<br>
			<li>
				프로젝트 : Most Challenging Tetris
			</li>
		<br>
		<h2 style="border-bottom: 1px solid #d8dee3; color: #282d33;"> 🤗 팀원 소개 </h2>	
			<li>
				김지관, 우지음, 천지민, 안선영
			</li>
		<br>
		<h2 style="border-bottom: 1px solid #d8dee3; color: #282d33;"> 💪 협업 방식 </h2>
			<ul>
				<li>자료 조사 및 아이디어 도출(15분)</li>
				<li>투표를 통해 주제 정하기</li>
				<li>격자 보드UI, 블록 모양 및 CSS, 떨어지는 블록 좌우로 위치 이동, 테트리스 블록 고정, 게임오버 역할 분담</li>
				<li>실시간 Slack을 통해 진행상황 공유</li>
				<li>Github Branch를 통해 완성된 코드 Push</li>
				<li>README.md에 프로젝트 정리 및 마무리</li>
			</ul>
   	<br>
		<h2 style="border-bottom: 1px solid #d8dee3; color: #282d33;"> 🔥 기능 시연 </h2>
	    	<img src="https://github.com/woorifisa-service-dev-2nd/frontend-5st-tetristeam/assets/66014764/4061ed9c-9bbe-4896-b35e-c53853a91b0b">
	<br>
		<h2 style="border-bottom: 1px solid #d8dee3; color: #282d33;"> 🎯 핵심 기능 설명 및 구현 방법 </h2>
		<br>	
		<h2 style="border-bottom: 1px solid #d8dee3; color: #282d33;"> 🚀 트러블 슈팅 </h2>
	    	<h3>- 블록의 위치 이동시 이동이 가능한 자리인지 판단의 어려움</h3>
		<p>이동중인 블록, 고정된 블록을 판단하는 요소를 어떻게 지정할지 고민이었고, 현재 움직이고있는 Element의 클래스로 moving과 finish를 추가하고 제거하는 과정을 통해 색상을 변경 시킴으로써 해결하였습니다.</p><br>
   		
		target.classList.add(type, 'moving') // 이동중인 블록에 moving 클래스 추가
		
		// 이동완료된 요소에 moving클래스 제거 후 finish 클래스 추가
		const temp = document.querySelectorAll('.moving')
		    temp.forEach((block) => {
		        block.classList.remove('moving')
		        block.classList.add('finish')
		    });
      	<br>
       
<h2 style="border-bottom: 1px solid #d8dee3; color: #282d33;"></h2><br>

<h3>- 방향 조작 코드</h3>
	    	<p>Keycode를 활용하여 작성하고자 했지만, Javascript ES6 버전에서 keyboard 이벤트가 지원하지 않음, keydown이벤트를 사용하여 ArrowRight, ArrowLeft, ArrowDown, ArrowUp을 사용하여 좌, 우, 하, 상(블록 방향 변경), Spacebar(dropBlock) 키보드로 조작할 수 있도록 구현하였다.</p><br>
	    
		document.addEventListener('keydown', (event) => {
		    switch (event.key) {
		        case 'ArrowRight':
		            moveBlock('m', 1)
		            break
		        case 'ArrowLeft':
		            moveBlock('m', -1)
		            break
		        case 'ArrowDown':
		            moveBlock('n', 1)
		            break
		        case 'ArrowUp':
		            changeDirection()
		            break
		        case ' ':
		            dropBlock()
		            break
		        default:
		            break
		    }
		});
  <br>
		<h2 style="border-bottom: 1px solid #d8dee3; color: #282d33;"> ✨ 느낀점 </h2>
	    	<li>우지음 : 기능 구현을 어떻게 할지 모르겠어서 구글링해서 방법을 참고 했는데, 남의 코드 이해하는게 가장 어려웠습니다. 하지만 코드를 이해하고 분석해서 순서도를 작성해본 것 은 의미있었습니다.</li>
	    	<li>안선영 : jascript ES6 버전에서 keyboard이벤트가 지원하지 않는 기능이 있어
지원하는 방식을 찾아서 코드를 새로 짜보았는데, 프로퍼티 에러가 계속 발생하였습니다. 결국 기존 코드 방식을 사용해야 했던 아쉬움이 남았습니다.  Javascript가 익숙해 질 수 있도록 공부를 하여, 다음 프로젝트를 할 때는 완벽하게 구현할 수 있도록 하고싶습니다.</li>
	    	<li>천지민 : javascript와 css에 익숙하지 않아서 원하는 대로 기능이 작동하지 않아 많은 어려움을 겪었지만 팀원들이 제 부족한 부분을 채워주어 많이 배우게 되었습니다. 또한 git과 github 같은 협업 툴을 처음 사용해 봤는데 원활한 협업을 위해 협업 툴들도 중요하다는 것을 알게 되어 앞으로 더 공부해 봐야겠다는 생각을 하게 되었습니다.</li>
	    	<li>김지관 : 코드를 처음부터 체계 없이 변수명을 지정하여 실행이 안되는 오류를 겪어 scope의 중요성을 체감하였으며 협업도구인 git을 처음 활용하여 익숙하지 않아 힘들었는데 이번 과제로 인해 협업도구의 중요성 또한 체감하였습니다.</li>
	<br>
 	
<div style="text-align: left;">
    <h2 style="border-bottom: 1px solid #d8dee4; color: #282d33;"> 🛠️ Tech Stacks </h2> <br> 
    <div style="margin: ; text-align: left;" "text-align: left;"> <img src="https://img.shields.io/badge/Javascript-F7DF1E?style=for-the-badge&logo=Javascript&logoColor=white">
          <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=HTML5&logoColor=white">
          <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=CSS3&logoColor=white">
          </div>
    </div>
    
