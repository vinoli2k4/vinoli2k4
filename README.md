import { launch } from "puppeteer";

export const screenshotWithPuppeteer = async () => {
  const browser = await launch({ headless: false }); // khởi tạo browser
  const page = await browser.newPage();  // tạo một trang web mới

  await page.goto("https://news.sun-asterisk.com/vi"); // điều hướng trang web theo URL

// chụp ảnh trang web
  await page.screenshot({
    path: "sun.png",
  });

  await browser.close(); // đóng trang web 
};

