

namespace QA.Web.SportsContent.ExtraV2.Builders
{
    public class PlayerImagesBuilder
    {
        private string _loggedInMinimumBetNotMetImage;
        private string _loggedInNoStreamsAvailableImage;
        private string _loggedInUnfundedAccountImage;

        private PlayerImagesBuilder(
            string loggedInMinimumBetNotMetImage,
            string loggedInNoStreamsAvailableImage,
            string loggedInUnfundedAccountImage)
        {
            _loggedInMinimumBetNotMetImage = loggedInMinimumBetNotMetImage;
            _loggedInNoStreamsAvailableImage = loggedInNoStreamsAvailableImage;
            _loggedInUnfundedAccountImage = loggedInUnfundedAccountImage;
        }

        public static PlayerImagesBuilder Default()
        {
            return new PlayerImagesBuilder(string.Empty, string.Empty, string.Empty);
        }

        public PlayerImagesBuilder LoggedInMinimumBetNotMetImage(string loggedInMinimumBetNotMetImage)
        {
            _loggedInMinimumBetNotMetImage = loggedInMinimumBetNotMetImage;
            return this;
        }

        public PlayerImagesBuilder LoggedInNoStreamsAvailableImage(string loggedInNoStreamsAvailableImage)
        {
            _loggedInNoStreamsAvailableImage = loggedInNoStreamsAvailableImage;
            return this;
        }

        public PlayerImagesBuilder LoggedInUnfundedAccountImage(string loggedInUnfundedAccountImage)
        {
            _loggedInUnfundedAccountImage = loggedInUnfundedAccountImage;
            return this;
        }

        public PlayerImages Build()
        {
            return new PlayerImages(
                _loggedInMinimumBetNotMetImage,
                _loggedInNoStreamsAvailableImage,
                _loggedInUnfundedAccountImage);
        }
    }
}
