# Edulastic-Cheats
***********
Another one of my bookmarklets


javascript:(() => {
    const selection = window.getSelection();
    if (!selection.anchorNode) return;
    
    const contentdiv = document.querySelector('div.edulastic-multipleChoice-container.edulastic-question-container' in selection.anchorNode.parentNode ? selection.anchorNode.parentNode.querySelector('div.edulastic-multipleChoice-container.edulastic-question-container') : selection.anchorNode.parentNode.parentNode.querySelector('div.edulastic-multipleChoice-container.edulastic-question-container'));
    
    const questions = contentdiv.querySelectorAll('.edulastic-multipleChoice-container > div');
    const answers = [];
    
    for (let i = 0; i < questions.length; i++) {
        const question = questions[i].querySelector('.edulastic-multipleChoice-container-text');
        const answer = questions[i].querySelector('.edulastic-multipleChoice-container-option:checked').textContent;
    
        if (question && answer) {
            answers.push({ question, answer });
        }
    }
    
    console.log(answers);
})();
