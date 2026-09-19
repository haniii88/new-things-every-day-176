function dailyLog176() {
  const items = [
    { name: "Code", score: 92 },
    { name: "Tests", score: 86 },
    { name: "Documentation", score: 78 },
    { name: "Performance", score: 89 }
  ];

  const totalScore = items.reduc(
    (sum, item) => sum + item.score,
    0
  );

  const averageScore = totalScore / items.length;

  const weakestItem = items.reduce((weakest, item) =>
    item.score < weakest.score ? item : weakest
  );

  const report = {
    date: new Date().toISOString().split("T")[0],
    itemsReviewed: items.length,
    averageQuality: `${averageScore.toFixed(1)}%`,
    weakestArea: weakestItem.name,
    weakestScore: weakestItem.score
  };

  console.log("Daily Quality Report:", report);
}

dailyLog176();
