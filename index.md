---
layout: page
title: Home
---

<div class="matu-countdown">
	<div>Encore <span id="js-countdown-lessons">?</span> leçons et <span id="js-countdown-exams">?</span> examens avant la fin de ma matu !</div>
	<div class="threshold">Prochaine étape dans <span id="js-countdown-threshold">?</span></div>
	<div class="remark">Comment ça, je ferais mieux de réviser ?</div>
</div>

<div class="clark-speaking">
<div class="speech-bubble" markdown="1">

Bienvenue sur mon site !

Vous trouverez ici une présentation des différents projets que j'ai réalisé.
Utilisez le menu en haut pour parcourir les catégories.

D'autres choses arriveront sur le site lorsque j'aurai le temps ;-)

*Clark Winkelmann*

</div>
</div>

<script>

/**
 * Les dates de fin des leçons de ma dernière semaine
 */
var lessons = [
	'2016-06-06T08:15:00', '2016-06-07T08:15:00', '2016-06-08T08:15:00', '2016-06-09T08:15:00', '2016-06-10T08:15:00',
	'2016-06-06T09:05:00', '2016-06-07T09:05:00', '2016-06-08T09:05:00', '2016-06-09T09:05:00', '2016-06-10T09:05:00',
	'2016-06-06T09:55:00', '2016-06-07T09:55:00', '2016-06-08T09:55:00', '2016-06-09T09:55:00', '2016-06-10T09:55:00',
	'2016-06-06T10:55:00', '2016-06-07T10:55:00', '2016-06-08T10:55:00', '2016-06-09T10:55:00', '2016-06-10T10:55:00',
	'2016-06-06T11:45:00', '2016-06-07T11:45:00', '2016-06-08T11:45:00', '2016-06-09T11:45:00', '2016-06-10T11:45:00',
	'2016-06-06T12:35:00',                        '2016-06-08T12:35:00',
	                       '2016-06-07T13:20:00',                        '2016-06-09T13:20:00',
	                       '2016-06-07T14:10:00', '2016-06-08T14:10:00', '2016-06-09T14:10:00',
	'2016-06-06T15:00:00', '2016-06-07T15:00:00', '2016-06-08T15:00:00',
	'2016-06-06T15:55:00',                        '2016-06-08T15:55:00',
];

/**
 * Les dates de fin de mes examens
 */
var exams = [
	'2016-06-13T11:00:00',
	'2016-06-13T15:00:00',
	'2016-06-13T17:00:00',
	'2016-06-14T09:50:00',
	'2016-06-14T11:10:00',
	'2016-06-15T10:30:00',
	'2016-06-16T15:30:00',
	'2016-06-16T17:15:00',
	'2016-06-20T13:50:00',
	'2016-06-21T11:40:00',
];

/**
 * Date de la prochaine étape
 */
var nextThreshold = null;


/**
 * Recalcule les totaux de leçons et examens restants
 */
function computeWhatsLeft()
{
	var now = (new Date()).getTime();

	// Leçons restantes
	var lessonsLeft = lessons.filter(function(time) {
		return (new Date(time)).getTime() > now;
	});
	var numberOfLessonsLeft = lessonsLeft.length;

	// Examens restants
	var examsLeft = exams.filter(function(time) {
		return (new Date(time)).getTime() > now;
	});
	var numberOfExamnsLeft = examsLeft.length;

	// Toutes les étapes restantes par ordre chronologique
	var incomingThresholds = lessonsLeft.concat(examsLeft);
	if(incomingThresholds.length > 0) {
		nextThreshold = new Date(incomingThresholds.sort(function(a, b) {
			return (new Date(a)).getTime() > (new Date(b)).getTime();
		})[0]); // get first elem
	} else {
		nextThreshold = null;
	}

	// Update
	document.getElementById('js-countdown-lessons').innerHTML = numberOfLessonsLeft;
	document.getElementById('js-countdown-exams').innerHTML  = numberOfExamnsLeft;
}

/**
 * Met à jour le temps restant jusqu'à la prochaine étape
 */
function updateThreshold()
{
	// Se rafraîchit toutes les 10 secondes
	window.setTimeout(function() {
		window.requestAnimationFrame(updateThreshold);
	}, 10 * 1000);

	// Si null on n'affiche rien
	if(nextThreshold == null) {
		document.getElementById('js-countdown-threshold').innerHTML  = '??';
		return;
	}

	// Temps restant en secondes
	var timeLeft = (nextThreshold.getTime() - (new Date()).getTime()) / 1000;

	// Si le délai est atteint on fait recalculer le restant
	if(timeLeft < 0) {
		computeWhatsLeft();
		return;
	}

	// Temps dans les différentes unités
	var days    = Math.floor(timeLeft / (60 * 60 * 24));
	var hours   = Math.floor(timeLeft % (60 * 60 * 24) / (60 * 60));
	var minutes = Math.floor(timeLeft % (60 * 60)      / (60));

	// Valeurs à afficher
	var display = [];
	if(days > 0   ) { display.push(days    + ' jours'); }
	if(hours > 0  ) { display.push(hours   + ' heures'); }
	display.push(minutes + ' minutes');

	// Update
	document.getElementById('js-countdown-threshold').innerHTML  =  display.join(', ');
}

// Go !
computeWhatsLeft();
updateThreshold();

</script>