Hello, my name is Muhammad Naufal Salman. You can call me Ufal.

I'm 23 years old college student living in Indonesia who love computers since I was a kid. Besides in college, I also writing cool stuff, making music, translating stuff I love. I have a small middle east shop at home too, and I run a side gig for translation and writing commission.

I'm writing articles on my blog, making YouTube video and a podcast show with variety of topics I'm interested in. I made this blog to publish my articles in English.

I have many hobbies and interests, mainly such as retro computer, Japanese modern culture, food technology, and linguistics. Loves Linux (I still mainly on Windows, though), open source software, web development, indieweb, virtual YouTuber, and doujin music. I also following Touhou Project, Arknights, iDOLM@STER, NIJISANJI, KAMITSUBAKI STUDIO.

I make my articles, video and content under Retrospective Klaten, my creative home studio.

I will available on Twitter at [@ufalsalman](https://x.com/ufalsalman) and Fediverse at [@ufal@misskey.id](https://misskey.id/ufal) (Indonesian) or [@ufal@mastodon.social](https://mastodon.social/ufal) (English). Visit my website if want to, [www.ufal.my.id](https://www.ufal.my.id). Hit me up on halo@ufal.my.id if want to say something.

<script>
  const username = "ufalsalman";
const apiKey = "5d626e712ed69872285be7cd3da8f313";

async function fetchRecentSong() {
    try {
        const response = await fetch(`https://ws.audioscrobbler.com/2.0/?method=user.getrecenttracks&user=${username}&api_key=${apiKey}&format=json&limit=1`);
        const data = await response.json();
            
        if (data.recenttracks && data.recenttracks.track.length > 0) {
            const song = data.recenttracks.track[0];
            const songTitle = song.name;
            const artist = song.artist['#text'];
            const album = song.album['#text'];
            const albumArt = song.image[2]['#text'];

            document.getElementById("lastfmrecent").innerHTML = `
                <div style="display: flex; align-items: center;">
                    <img src="${albumArt}" alt="Album Art" style="width: 72px; height: 72px; margin-right: 15px; border-radius:10px;">
                    <div>
                        <p><b>${songTitle}</b><br>
                        <a href="https://www.last.fm/music/${artist}" target="_blank">${artist}<br>
                        <a href="https://www.last.fm/music/${artist}/${album}" target="_blank">${album}</a></p>
                    </div>
                </div>
            `;
        } else {
            document.getElementById("lastfmrecent").innerHTML = "<p>Tidak ada lagu terbaru.</p>";
        }
    } catch (error) {
        console.error("Error fetching song:", error);
        document.getElementById("lastfmrecent").innerHTML = "<p>Gagal menampilkan lagu terbaru.</p>";
    }
}

fetchRecentSong();

setInterval(fetchRecentSong, 15000);
</script>
<div id="lastfmrecent"></div>

<!---
ritokatsuga/ritokatsuga is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
